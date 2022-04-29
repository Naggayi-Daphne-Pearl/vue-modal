<template>
  <div class="home">
    <h1>Home</h1>
    <h3>Computations</h3>
    <input type="text" v-model="search">
    <p>search here - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
   
    
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'home',
  setup() {
    const search = ref('')
    const names = ref(['daphne', 'naggayi', 'pearl']); 
    watch(search, () => {
      console.log('watch function run')
    })
    const matchingNames = computed(()=> {
      return names.value.filter((name) => name.includes(search.value))
    })

    return { names, search, matchingNames }

  } 
 
}
</script>
