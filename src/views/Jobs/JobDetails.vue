<template>
  <div v-if="job">
    <h1>{{ job.title }}</h1>
    <!-- <p>The job ID is {{ $route.params.id}}</p>     syntax for use with route object -->
    <p>The job ID is {{ id }}</p>
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p>Loading job...</p>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      // id: this.$route.params.id ---> this is now set up as prop
      job: null,
      // THIS WORKS for null render error on mount without using v-if
      // job: {
      //   title: '',
      //   id: this.id,
      //   details: ''
      // }
    };
  },
  mounted() {
    // console.log("job mount");
    fetch("http://localhost:3000/jobs/" + this.id)
      .then((res) => res.json())
      .then((data) => {
        (this.job = data)
        // console.log(this.job)
        })
      .catch((error) => console.log(error.message));
  },
};
</script>

<style>
</style>