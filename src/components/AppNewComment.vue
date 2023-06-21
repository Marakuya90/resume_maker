<template>
<form @submit="$emit('postingComment')">
  <input class="form-control" type="text" placeholder="Введите имя">
  <textarea class="form-control" placeholder="Введите текст комментария"></textarea>
  <button class="btn btn-success">Отправить</button>
</form>
</template>

<script>
export default {
  name: "AppNewComment.vue",
  emits: ['postingComment']
}
</script>

<style scoped>

</style>
