<template>
  <div class="home">
    <h1>Home page</h1>
    <p>My name is {{ name }}. I am {{ age }}</p>
    <button @click="handleClick">Click me</button>
    <button @click="age++">ADD AGE</button>
    
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'home',
  setup() {
    //const p = ref(null)

    // when we use ref to surround a value it becomes reactive
    const name = ref('daphne')
    const age = ref(24)

    
    const handleClick = () => { 
      name.value = 'pearl'
      age.value = 25
     
    }

    return{name: name, age:age, handleClick}

  } 
 
}
</script>
