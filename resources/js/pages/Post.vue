<template>

    <div class="card-body d-flex flex-column">
        <h5 class="card-title">{{title}}</h5>
        <p class="card-text">{{ truncateText(content)}}</p>
        <button type="button" class="btn btn-outline-success">{{category ? category.name : '&nbsp;'}}</button>
        <router-link class="btn btn-primary" :to="{name: 'single-post', params: {slug: slug}}">Mostra dettagli post</router-link>

    </div>
    
</template>

<script>
    export default {
        name: "Post",
        props: ["title", "content", "slug", "category", "tags"],
        data(){
            return{
                lunghezzaContent: 40
            }
        },

        methods:{
            truncateText(text){
                if(text.length > this.lunghezzaContent){
                    return text.substring(0, this.lunghezzaContent) + "...";
                }else{
                    return text;
                }
            }
        }
    }
</script>

<style>

</style>