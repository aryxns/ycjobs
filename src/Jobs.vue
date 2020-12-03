<template>
	<div class="main">
        <head>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no"> 
        </head>
		<h1>YC Jobs</h1>
        <hr style="width:50%;height:2px;box-shadow:10px">
        <div class>
        <div class="search-bar">
        <input class="searchbox" type="text" v-model="search" placeholder="Search Here"> 
        <b-button class="b1" variant="outline-primary" @click="getSearch">Search Role</b-button>
        <b-button class="b2" variant="outline-primary" @click="getPosts">Load Latest</b-button>
        </div>
        <br>
        <div v-for="(post, idx) in posts" :key="idx" class="cards">
            <b-card data-aos="zoom-in-up">
                <h4>{{post.title}}</h4>
                <br>
                <b-button class="card-link" v-on:click="gotosite(post.content)">Apply</b-button>
            </b-card>
        </div>
    </div>
	</div>
</template>

<script>

import AOS from 'aos'
import 'aos/dist/aos.css'
//import FooterPage from './Footer.vue'

AOS.init()
// import {APIService} from '../APIService';
// const apiService = new APIService();
import axios from 'axios';
//import SearchBar from './Search.vue'

window.addEventListener('load', AOS.refresh)

export default {
    name: 'Jobs',
    components: {
        //'footer': FooterPage
    },

    data() {
        return {
            posts: [],
            search: ''
        }
    },

    methods: {
        getSearch: function() {
            axios.post('https://rha02f.deta.dev/search', {
                search: this.search
            }).then(response => {
                this.posts = response.data
                console.log(response.data)
            })
        },
        gotosite(url){
            window.open(url)
        },
        getPosts: function() {
             axios.get('https://rha02f.deta.dev/posts').then(response => {
                this.posts = response.data
                console.log(response.data) 
            })
        },
    },
    mounted() {

    },
};
</script>
<style scoped>
.main {
    font-weight: bold;
}

.cards {
    width: 50%;
    margin: auto;
    padding: 10px;
    box-shadow: 10px;
    border: black;
}
.search-bar {
    display: flex;
    margin: auto;
    justify-content: space-between;
    width: 30%;
    margin: 0 auto;
    padding: 10px;
}
.card-link {
    color: #1E90FF;
    border: 1.5px solid #1E90FF;
    background-color: white;
}
.card-link:hover {
    color: white;
    background-color: #1E90FF;
}
.b2 {
    color: #1E90FF;
    border: 1.5px solid #1E90FF;
}
.b1 {
    color: #1E90FF;
    border: 1.5px solid #1E90FF
}
</style>
