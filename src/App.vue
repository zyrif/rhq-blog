<template>
    <div class="container">
        <app-header></app-header>
        <app-post-grid v-bind:posts="posts" ></app-post-grid>
        <app-new-post></app-new-post>
    </div>
</template>

<script>
import PostGrid from './components/PostGrid.vue'
import Header from './components/Header.vue'
import NewPost from './components/NewPost.vue'
import axios from 'axios';

export default {
    data() {
        return {
            posts: ['An Example Post']
        }
    },

    created() {
        axios.get("https://rhq-blog.firebaseio.com/posts.json")
        .then(res => {
            const data = res.data;
            const posts = [];
            for (let key in data){
                const post = data[key];
                post.id = key;
                posts.push(post)
            }
            this.posts = posts;
        })
        .catch(error => console.error(error))
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
