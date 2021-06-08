<template>
  <h1>Job Details Page</h1>
  <!-- <p>The job ID is {{ $route.params.id}}</p>     syntax for use with route object -->
  <p>The job ID is {{ id }}</p>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      // id: this.$route.params.id ---> this is now set up as prop
    };
  },
};
</script>

<style>
</style>