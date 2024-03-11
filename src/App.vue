<script>
import './styles/index.scss'
import Header from './components/Header.vue'
import CardUser from './components/CardUser.vue'

export default {
  components: {
    Header,
    CardUser
  },
  data() {
    return {
      darkMode: false,
      usuario: null
    };
  },
  methods: {
    toggleTheme() {
      this.darkMode = !this.darkMode;
    },
    atualizarUsuario(usuario) {
      this.usuario = usuario;
    }
  }
}
</script>

<template>
  <body :class="{ 'dark-mode': darkMode }">
    <div class="container">
      <Header @toggle-theme="toggleTheme" @usuario-encontrado="atualizarUsuario" :class="{ 'dark-header': darkMode }" />
      <CardUser :class="{ 'dark-card': darkMode }" :usuario="usuario" />
    </div>
  </body>
</template>
