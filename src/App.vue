<template>
  <div id="app">
    <span>View this digitally: <a id="url" :href="siteUrl">{{ siteUrl }}</a></span>
    <Header/>
    <Certs/>
    <Skills/>
    <Experience/>
    <center>
      Thank you for viewing. This resume is build in <i class="fab fa-vuejs"></i> and hosted on <i class="fab fa-github"></i> <a :href="githubUrl">{{ githubUrl }}</a>
    </center>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Certs from './components/Certs.vue'
import Skills from './components/Skills.vue'
import Experience from './components/Experience.vue'

export default {
  name: 'app',
  components: {
    Header,
    Certs,
    Skills,
    Experience
  },
  data() {
    return {
      githubUrl: 'https://github.com/ryangrossGitHub/resume',
      siteUrl: 'https://d1vav2tr76x9eu.cloudfront.net'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
center {
  margin: 1rem;
}
span {
  font-size: 0.9rem;
}
</style>
