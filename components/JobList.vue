<template>
  <ul class="job-list">
    <job-list-item v-for="job in jobs" :key="job.id" :job="job" />
  </ul>
</template>

<script>
import JobListItem from './JobListItem.vue'

export default {
  components: {
    JobListItem
  },
  props: {
    jobs: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>
.job-list {
  margin: 2rem 0 3rem;
  list-style: none;
  padding: 0;
}
</style>
