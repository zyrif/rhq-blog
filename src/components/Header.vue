<template>
    <div class="row">
        <div class="col-lg-8">
            <h1 class="title">Raven's HQ Blog</h1>
        </div>
        <div class="col-sm-4">
            <button class="btn btn-primary" id="new-btn" v-on:click="NavigateToNewPost">New</button>
        </div>
    </div>
</template>


<script>
export default {
    methods: {
        NavigateToNewPost() {
            this.$router.push({path: '/New'})
        }
    }
}
</script>

<style>
    .title, .btn {
        margin: 25px auto;
    }

    #new-btn {
        float: right;
    }
</style>
