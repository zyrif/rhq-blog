<template>
    <div class="row">
        <app-post v-for="(post,index) in posts" v-bind:key="index"> {{ post }} </app-post>
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
