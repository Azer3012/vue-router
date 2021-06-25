<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <router-link :to="{ name: 'JobDetail', params: { id: job.id } }">
      <h2>{{ job.title }}</h2>
    </router-link>
  </div>
</template>
<script>
export default {
  data() {
    return {
      jobs: [
        { id: 1, title: "UX Designer", details: "lorem" },
        { id: 2, title: "web Developer", details: "lorem" },
        { id: 3, title: "UX Vue Developer", details: "lorem" },
      ],
    };
  },
};
</script>
<style>
</style>