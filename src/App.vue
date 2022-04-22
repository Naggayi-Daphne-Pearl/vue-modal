<template>
  <h1>{{ title }}</h1>
  <Modal :header="header" :text="text"/>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first vue App:)', 
      header: 'Sign me up', 
      text: 'naggayi DAPHNE'
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
