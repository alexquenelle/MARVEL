<template lang="html">
    <div>
        <h3>Marvel's characters </h3>
        <input type="text" v-model="search" placeholder="search heroes"/>
        <p><br></p>
        <ul>
            <li v-for="characters in filteredCharacters">
                <router-link :to="{ name: 'character', params: { id: characters.id}}">{{characters.name}}</router-link>
            </li>
        </ul>
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
</style>