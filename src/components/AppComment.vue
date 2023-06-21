<template>
  <div
      class="card mb-2 p-3"
      v-for="comment in comments"
      :key="comment.id">
    <h3>{{ comment.name }}</h3>
    <hr/>
    <p>{{ comment.text }}</p>
  </div>

</template>

<script>
export default {
  name: "AppComment.vue",
  props:['comments']
}
</script>

<style scoped>

</style>
