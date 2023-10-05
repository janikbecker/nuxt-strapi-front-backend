<template>
    <h1>{{ post }}</h1>
</template>

<script setup lang="ts">
const { findOne } = useStrapi();
const { slug } = useRoute().params;

const { data: post } = await useAsyncData(
    'post',
    () => findOne('posts', {
        filters: {
            Slug: { $eq: slug }
        }
    }),
    {
        transform: (data: any) => {
            if (data.data[0]) {
                return data.data[0].attributes;
            } else {
                return null;
            }
        },
    });
</script>