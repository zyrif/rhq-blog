<template>
    <div class="container">
        <app-header></app-header>
        <app-post-grid v-bind:posts="posts" ></app-post-grid>
        <!-- <app-new-post></app-new-post> -->
    </div>
</template>

<script>
import PostGrid from './components/PostGrid.vue'
import Header from './components/Header.vue'
import NewPost from './components/NewPost.vue'

export default {
    data() {
        return {
            posts: ['An Example Post']
        }
    },

    components: {
        appHeader: Header,
        appPostGrid: PostGrid,
        appNewPost: NewPost
    }
}
</script>

<style>
    .container {
        margin: 25px auto;
    }
</style>
