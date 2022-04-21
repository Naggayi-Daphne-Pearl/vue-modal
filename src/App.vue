<template>
  <h1>{{ title }}</h1>
  <modal />
</template>

<script>
import modal from './components/modal.vue'
export default {
  name: 'App',
  components: { modal },
  data() {
    return {
      title: 'My first vue App:)'
    }
  }, 
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd ;
  display: inline-block;
  padding: 10px;
  text-transform: capitalize;
}
</style>
