<template>
    <NuxtLink :to="post.Slug" class="post-sneak">
        <h3>{{ post.Title }}</h3>
        <p>{{ post.Intro }}</p>
    </NuxtLink>
</template>

<script lang="ts" setup>
defineProps<{
    post: Post;
}>();

</script>