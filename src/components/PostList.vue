<template>
  <div v-if="posts.length > 0">
    <h3>Список пользователе</h3>
    <post-item class="post" v-for="post in posts" :post="post" :key="post.id" @remove="$emit('remove', post)"/>
  </div>
  <h2 v-else style="color: red">
    Список пуст
  </h2>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
};
</script>

<style scoped></style>
