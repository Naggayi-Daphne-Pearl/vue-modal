<template>
  <h1>JOBS</h1>
  <div v-for="job in jobs" :key ="job.id">
      <!--Dynamic links-->
      <router-link :to="{name:'JobDetails', params:{ id:job.id}}">
          <h2>{{ job.title }}</h2>
      </router-link>
  </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                {title: 'UX DESIGNER', id: 1, details: 'lorem'},
                {title: 'Developer', id: 2, details: 'lorem'},
                {title: 'vue developer', id: 3, details: 'lorem'},
            ]
        }
    }

}
</script>

<style>

</style>