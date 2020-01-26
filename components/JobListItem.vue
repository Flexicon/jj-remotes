<template>
  <li class="job-list-item">
    <a :href="job.url" target="_blank" rel="noopener noreferrer">{{
      job.title
    }}</a>
  </li>
</template>

<script>
export default {
  props: {
    job: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.job-list-item {
  padding: 1rem;
  background: white;
  margin-bottom: 1rem;
  box-shadow: 0px 3px 5px 0px #aaa;
  border-radius: 8px;
}

.job-list a {
  color: cadetblue;
  text-decoration: none;
}

.job-list a:hover {
  color: #127d79;
  text-decoration: underline;
}
</style>
