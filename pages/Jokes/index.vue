<template>
    <div>
        <SearchJoke v-on:search-text="searchText" />
        <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
    </div>
</template>
<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue';
import SearchJoke from '../../components/SearchJoke.vue';

export default {
    data(){
        return{
            jokes:[]
        }
    },
    layout: 'jokes',
    components: { 
        Joke,
        SearchJoke 
    },
    async created(){
        const config = {
            headers: {
                'Accept':'application/json'
            }
        }
        try{
            const res = await axios.get('https://icanhazdadjoke.com/search',config);
            this.jokes = res.data.results;
        }
        catch(er){
            console.log(err)
        }
        
    },
    methods:{
        async searchText(text){
            const config = {
                headers: {
                    'Accept':'application/json'
                }
            }
            try{
                const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`,config);
                this.jokes = res.data.results;
            }
            catch(er){
                console.log(err)
            }
        }
    },
    head(){
        return {
            title: 'Dad Jokes',
            meta:[
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best palce for corny dad jokes'
                }
            ]
        }
    }
}
</script>