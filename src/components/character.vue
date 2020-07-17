<template lang="html">
    <div>
        <div class="content">
            <div v-for="char in character">
                <h3>{{char.name}}</h3>
                <p>{{char.description}}</p>
            </div>
        </div>
        <img :src="url" alt="" class="image">
            <br>
        <button class="back-button"><router-link to="/" class="text">Back</router-link></button>
        <br><br>
    </div>
</template>

<script>    
import {public_key} from '../marvel'
import axios from 'axios'

export default {
    name: 'Character',

    data(){
        return{
            character: [],
            url: '',
            size: 'standard_xlarge.jpg',
        }
    },

    mounted(){
        this.getCharacter()
    },

    methods: {
        getCharacter: function(){
            var characterId = this.$route.params.id
            axios.get(`https://gateway.marvel.com/v1/public/characters/${characterId}?apikey=${public_key}`)
            .then((result) => {
                console.log(result)
                result.data.data.results.forEach((item) => {
                    this.character.push(item)
                    this.url = `${item.thumbnail.path}/${this.size}`
                    console.log(this.url)
                });
            })
            .catch((error) => {
                console.log(error)
            })
        }
    }
}
</script>

<style lang="css">

.content{
    margin: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.image{
    border-radius: 20px;
}

.back-button {
    margin-top: 40px;
    border-radius: 25px;
    background-color: grey;
    font-size: 30px;
    width: 300px;
    border: 3px solid white
}

.text {
    color: white;
    font-family: 'Lucida Console', Monaco, monospace;
}
</style>