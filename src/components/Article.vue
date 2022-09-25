<template>
    <div class="main d-flex justify-content-center">
        <div id="app w-100">
            <h1>Article {{ id }}</h1>
            <div class="article bg-light p-5">
                <div class="article-title d-flex align-item-middle">
                    <h3 class="vignette"><div>{{ titre.title }}</div></h3><h3 class="titre">{{ titre.title }}</h3>
                </div>
                <div class="commentaires" v-for="(commentaire, index) in commentaires" :key="index">
                    <h5>{{ commentaire.name }}</h5>
                    <a href="mailto:">{{ commentaire.email }}</a>
                    <p>{{ commentaire.body }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    props: {
        id: String
    },
    data() {
        return {
            titre: [],
            commentaires: []
        }

    },
    methods: {
        getArticleTitle() {
            const URL = " https://jsonplaceholder.typicode.com/posts/" + this.id
            axios
                .get(URL)
                .then(res => {
                    this.titre = res.data;
                })
        },

        getArticleComments() {
            const URL = "https://jsonplaceholder.typicode.com/posts/" + this.id + "/comments"
            axios
                .get(URL)
                .then(res => {
                    this.commentaires = res.data;
                })
        }
    },
    mounted() {
        this.getArticleTitle();
        this.getArticleComments();
    }
}
</script>

<style>
.vignette::first-letter {
    padding: none;  
}

</style>