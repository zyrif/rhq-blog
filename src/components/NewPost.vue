<template>
    <div>
        <div>
            <div class="row">
                <div class="col-lg-7">
                    <div class="form-group">
                        <label for="id-title-input">Title</label>
                        <input type="text" class="form-control" id="id-title-input" v-model="postData.subject">
                    </div>
                </div>
            </div>  

            <div class="row">
                <div class="col-lg-7">
                    <div class="form-group">
                        <label for="id-postcontent-input">Content</label>
                        <textarea class="form-control" id="id-postcontent-input" cols="30" rows="10" v-model="postData.content"></textarea>
                    </div>
                </div>
            </div>
            
        </div>
        <div class="row">
            <div class="col-lg-6">
                <button class="btn btn-danger">Delete</button>
            </div>
            <div class="col-lg-6">
                <button class="btn btn-primary" v-on:click="savePost">Save</button>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            postData: {
                subject: '',
                content: '',
            }
        }
    },

    methods: {
        savePost() {
            // console.log("Subject: " + this.post.subject);
            // console.log("Content: " + this.post.content);
            axios.post("https://rhq-blog.firebaseio.com/posts.json", this.postData)
            .then(res => {
                console.log(res)
                this.postData.subject = '';
                this.postData.content = '';
                if (res.statusText == "OK"){
                    alert("Posted Successfully")
                    
                }
            })
            .catch(error => console.error(error));
        }
    }
}
</script>

<style>

</style>
