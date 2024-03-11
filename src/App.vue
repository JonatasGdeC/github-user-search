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
      darkMode: false
    };
  },
  methods: {
    toggleTheme() {
      this.darkMode = !this.darkMode;
    }
  }
}
</script>

<template>
  <body :class="{ 'dark-mode': darkMode }">
    <div class="container">
      <Header @toggle-theme="toggleTheme" :class="{ 'dark-header': darkMode }" />
      <CardUser :class="{ 'dark-card': darkMode }" />
    </div>
  </body>
</template>
