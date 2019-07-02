<template>
    <div class="row">
        <app-post v-for="post in posts" v-bind:key="post.id"> {{ post.content }} </app-post>
    </div>
</template>

<script>
import Post from './Post.vue';

export default {
    props: ['posts'],
    components: {
        appPost: Post
    },
}
</script>

<style scoped>

</style>
