<template>
  <div class="container">
    <h1 class="title">
      Remote Job offers
    </h1>

    <job-list :jobs="jobs" />
  </div>
</template>

<script>
import JobList from '@/components/JobList.vue'

export default {
  components: {
    JobList
  },
  data() {
    return {
      jobs: []
    }
  },
  created() {
    this.fetchJobs()
  },
  methods: {
    async fetchJobs() {
      this.jobs = await this.$axios
        .get('https://scrape-jj-remotes.herokuapp.com/jobs')
        .then((res) =>
          res.data.map((job) => ({
            ...job,
            url: `https://justjoin.it/offers/${job.id}`
          }))
        )
    }
  }
}
</script>

<style>
.container {
  width: 1000px;
  max-width: 100%;
  margin: 0 auto;
  padding: 2rem 1rem;
}
</style>
