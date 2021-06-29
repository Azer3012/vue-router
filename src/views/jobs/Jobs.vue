<template>
  <h1>Jobs</h1>
  <div v-if="jobs.length">
    <div class="jobs" v-for="job in jobs" :key="job.id">
      <router-link :to="{ name: 'JobDetail', params: { id: job.id } }">
        <h2>{{ job.title }}</h2>
      </router-link>
    </div>
  </div>
  <div v-else>
    <p>Loadind jobs....</p>
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
    fetch("http://localhost:3000/jobs")
      .then((res) => res.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.log(err.message));
  },
};
</script>
<style>
.jobs{
  width: 50%;
  margin: 0 auto;
}
.jobs a{
  color: black;
  display: block;
  text-decoration: none;
  background-color: #ddd;
  padding: 5px 0;
  margin-bottom: 5px;
  transition: 0.5s;

}
.jobs a:hover{
  background: rgb(250, 247, 247);
  color: #42b983;
}
</style>