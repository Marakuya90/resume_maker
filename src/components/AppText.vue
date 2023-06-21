<template>
<hr>
<p>
  {{ text }}
</p>
</template>

<script>
export default {
  name: "AppText.vue",
  props: {
    text: String
  }
}
</script>

<style scoped>

</style>
