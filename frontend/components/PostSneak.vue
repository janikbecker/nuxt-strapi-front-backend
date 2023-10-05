<template>
    <NuxtLink :to="post.Slug" class="post-sneak">
        <h3>{{ post.Title }}</h3>
    </NuxtLink>
    <p>{{ post.Intro }}</p>
    <hr>
</template>

<script lang="ts" setup>
defineProps<{
    post: Post;
}>();

</script>