<template>
  <main>
    <div v-for="(post, index) in posts" :key="index">
      <h2>{{post.attributes.Title}}</h2>
      <p>{{post.attributes.user.data.attributes.username}}</p>
    </div>
  </main>
</template>
<script setup>
const { data } = await useFetch("http://localhost:1337/api/posts?populate=user");
const posts = data.value.data;
console.log(posts);
</script>
