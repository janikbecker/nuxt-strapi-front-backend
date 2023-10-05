<template>
    <div>
        <h1>Blog</h1>
        <p>Hier findest du alle meine Blogposts. Viel Spaß beim Lesen!</p>

        {{ posts }}

    </div>
</template>

<script setup lang="ts">
const { find } = useStrapi();

const { data: posts } = await useAsyncData('posts', () => find('posts'),
    {
        transform: (data: any) => {
            if (data.data) {
                return data.data.map((post: any) => post.attributes);
            }
        }
    }
);

</script>

<style scoped lang="scss"></style>