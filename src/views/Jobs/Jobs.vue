<template>
  <h1>Jobs</h1>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id">
      <router-link :to="{ name: 'JobDetails', params: { id: job.id } }"
        ><h2>{{ job.title }}</h2></router-link
      >
    </div>
  </div>
  <div v-else>
    <p>Jobs loading...</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    // console.log('jobs mount')
    fetch("http://localhost:3000/jobs")
      .then((res) => res.json())
      .then((data) => (this.jobs = data))
      .catch((error) => console.log(error.message));
  },
};
</script>

<style>
</style>