<template>
  <div class="home">
    <h1>Home page</h1>
    <p ref="p">My name is {{ name }}. I am {{ age }}</p>
    <button @click="handleClick">Click me</button>
    

  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'home',
  setup() {
    const p = ref(null)

    let name = 'daphne'
    let age = 24
    
    const handleClick = () => {
      console.log(p, p.value)
      p.value.textContent ='learning vue'
    }

    return{name: name, age:age, handleClick, p}

  }, 
  created() {
    console.log('created')

  }, 
  mounted() {
    console.log('mounted')

  }
}
</script>
