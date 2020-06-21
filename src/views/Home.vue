<template>
    <div class="home">
        <Characters />
    </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import Characters from '@/components/characters.vue'

export default {
    name: 'Home',
    components: {
        HelloWorld,
        Characters
    },

    methods:{
        getCharacters: function(){
            axios.get(`http://gateway.marvel.com/v1/public/chararcters?apikey=c2a8bc81cffc0beb1b454edba897c69d`)
        }
    }
}
</script>