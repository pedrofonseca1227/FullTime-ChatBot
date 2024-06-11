<template>
    <v-app>
      <v-app-bar>
        <v-app-bar-title>GPT UI</v-app-bar-title>
        <!-- <v-btn @click="toggleTheme" 
               :icon="theme.global.current.value.dark ? 
               'mdi-weather-night' : 'mdi-weather-sunny'">
        </v-btn> -->
      </v-app-bar>
      <v-main>
        <RouterView />
        <Chatbot />
      </v-main>
    </v-app>
  </template>
  
  <script>
  import { useTheme } from 'vuetify'
  import { RouterView } from 'vue-router'
  import Chatbot from './components/Chatbot.vue'  // Importa o componente Chatbot
  
  export default {
    components: {
      RouterView,
      Chatbot  // Adiciona o componente Chatbot aos componentes utilizados
    },
    setup() {
      const theme = useTheme()
      
      const toggleTheme = () => {
        theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
      }
      
      return { toggleTheme, theme }
    },
  }
  </script>
  