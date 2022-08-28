<template>
    <main>
        <h1>{{post.data[0].attributes.Title}}</h1>
    </main>
</template>
<script setup>
const route = useRoute()

const { data } = await useFetch(`http://localhost:1337/api/posts?Slug=${route.params.slug},populate=user`);
const post = data.value;
console.log(route.params.slug)
console.log(post.data)
</script>