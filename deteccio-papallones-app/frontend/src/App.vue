<template>
  <v-app>
    <v-main>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="6">
            <v-card class="elevation-12 pb-4">
              <v-toolbar color="primary" dark flat>
                <v-toolbar-title>Detector de Papallones</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <p class="mb-4">
                  Puja una fotografia d'una papallona per identificar-ne l'espècie amb el nostre model millorat.
                </p>
                <v-file-input
                  v-model="imatge"
                  label="Selecciona una imatge"
                  accept="image/*"
                  prepend-icon="mdi-camera"
                  @change="onFileChange"
                ></v-file-input>

                <v-img
                  v-if="previewUrl"
                  :src="previewUrl"
                  max-height="300"
                  class="mt-4 rounded-lg grey lighten-2"
                ></v-img>

                <div v-if="resultat" class="mt-6">
                  <v-divider class="mb-4"></v-divider>
                  <h2 class="text-h5 primary--text text-center">Resultat de la identificació</h2>
                  
                  <div class="text-center mt-2 mb-4">
                    <p class="text-h4 font-weight-bold">{{ resultat.especie }}</p>
                  </div>

                  <v-row align="center" class="mb-4">
                    <v-col cols="4" class="text-right font-weight-medium">Confiança:</v-col>
                    <v-col cols="8">
                      <v-progress-linear
                        v-model="resultat.confianca"
                        color="primary"
                        height="20"
                        rounded
                      >
                        <template v-slot:default="{ value }">
                          <span class="white--text font-weight-bold">{{ Math.ceil(value) }}%</span>
                        </template>
                      </v-progress-linear>
                    </v-col>
                  </v-row>

                  <v-alert border="left" colored-border color="primary" elevation="2" class="mt-4">
                    <div class="font-weight-bold mb-1">Descripció:</div>
                    <div>{{ resultat.descripcio }}</div>
                    <div v-if="resultat.habitat" class="mt-2">
                      <span class="font-weight-bold">Hàbitat:</span> {{ resultat.habitat }}
                    </div>
                  </v-alert>
                </div>

                <v-alert
                  v-if="error"
                  type="error"
                  class="mt-4"
                  dismissible
                >
                  {{ error }}
                </v-alert>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  color="primary"
                  size="large"
                  :loading="carregant"
                  :disabled="!imatge || carregant"
                  @click="identificar"
                >
                  Identificar papallona
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const imatge = ref(null)
const previewUrl = ref(null)
const resultat = ref(null)
const carregant = ref(false)
const error = ref(null)

const onFileChange = () => {
  if (imatge.value) {
    previewUrl.value = URL.createObjectURL(imatge.value)
    resultat.value = null
    error.value = null
  } else {
    previewUrl.value = null
  }
}

const identificar = async () => {
  if (!imatge.value) return

  carregant.value = true
  error.value = null
  resultat.value = null

  const formData = new FormData()
  formData.append('imatge', imatge.value)

  try {
    const response = await axios.post('http://localhost:3000/api/detectar', formData, {
      headers: {
        'Content-Type': 'multipart/form-data'
      }
    })
    resultat.value = response.data
  } catch (err) {
    error.value = err.response?.data?.error || 'S\'ha produït un error en connectar amb el servidor.'
  } finally {
    carregant.value = false
  }
}
</script>

<style>
/* Estils personalitzats */
</style>
