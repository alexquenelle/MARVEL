<template lang="html">
    <div>
        <p><br></p>
        <input class="search-bar" type="text" v-model="search" placeholder="Search..."/>
        <p><br></p>
        <div class="card-container">
            <div class="card" v-for="characters in filteredCharacters">
                <h3 class="char-name">{{characters.name}}</h3>
                <router-link :to="{ name: 'character', params: { id: characters.id}}">
                <a href="button" class="button1">View Hero</a>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
import { public_key, private_key } from '../marvel';
import axios from 'axios'
export default {
    name: 'Characters',

    data: function(){
        return{
            characters: [],
            search: '',
        }
    },

    mounted(){
        this.getCharacters()
    },

    computed:{
        filteredCharacters: function(){
            return this.characters.filter((characters) => {
                return characters.name.match(this.search)
            })
        }
    },

     methods:{
        getCharacters: function(){
            var search = this.search
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=1300&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=1200&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=1100&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=1000&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=1200&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=900&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=800&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=700&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=600&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=500&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=400&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=300&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=200&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=100&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            axios.get(`http://gateway.marvel.com/v1/public/characters?apikey=${public_key}&offset=0&limit=100`)
            .then((result) => {
                result.data.data.results.forEach((item) => {
                    console.log(item)
                    this.characters.push(item)
                })
            })
            .catch((error) => {
                console.log(error)
            })
        }
    }
}
</script>

<style lang="css">

.card-container{
    display: grid;
    grid-template-columns: auto;
    grid-gap: 30px;
    padding: 10px;
    font-size: 15px;
    text-align: center ;
    font-family: 'Lucida Console', Monaco, monospace;
}

.card{
    background-color:#F41C24;
    border-radius: 20px;
    height: 250px;
    font-family: 'Lucida Console', Monaco, monospace;
}

.search-bar{
    background-color:#F41C24;
    border-radius: 20px;
    font-size: 25px;
    width: 300px;
    font-family: 'Lucida Console', Monaco, monospace;
}

.button1{
    display: inline-block;
    padding:0.35em 1.2em;
    border:0.1em solid #FFFFFF;
    border-radius: 20px;
    box-sizing: border-box;
    font-family: 'Lucida Console', Monaco, monospace;
    color:#FFFFFF;
    font-size: 22px;
    text-align:center;
    width: 280px;
    height: 50px;
    margin-top: 35px;
}
.button1:hover{
    color:#000000;
    background-color:#FFFFFF;
}

.char-name{
    font-size: 30px;
    margin-top: 27px
}

</style>