<template>
    <div class="card text-center">
        <div class="card-header">Category</div>
        <div class="card-body">
            <h5 class="card-title"> {{ post.subject }}</h5>
            <h6 class="card-subtitle mt-2 mb-2 text-muted">Author</h6>
            <p class="card-text text-justified">{{ post.content }}</p>
        </div>
        <div class="card-footer">
            <a href="#" class="card-link float-right">Read More</a>
        </div>
    </div>
</template>

<script>
export default {
    props: ['post']
}
</script>

<style scoped>
    .card {
        width: 18rem;
        height: 20rem;
        margin: 20px 25px;
    }

</style>

