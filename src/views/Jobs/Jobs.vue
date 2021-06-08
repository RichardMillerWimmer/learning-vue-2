<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
      <router-link :to="{ name: 'JobDetails', params: {id: job.id}}"><h2>{{job.title}}</h2></router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        { title: "UX Designer", id: 0, details: "designs UX" },
        { title: "Web Developer", id: 1, details: "developes web apps" },
        { title: "Vue Developer", id: 2, details: "developes Vue apps" },
        { title: "React Developer", id: 3, details: "developes React apps" },
      ],
    };
  },
};
</script>

<style>
</style>