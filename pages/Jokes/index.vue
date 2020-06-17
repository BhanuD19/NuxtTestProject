<template>
    <div>
      <SearchJokes v-on:search-text="searchText" />
      <joke v-for="joke in jokes" :key="joke.id"
      :id="joke.id" :joke="joke.joke" />
    </div>
</template>

<script>
  import axios from "axios";
  import joke from "../../components/joke";
  import SearchJokes from "../../components/SearchJokes";
    export default {

        name: "index",
        components: {
            joke,
            SearchJokes
        },
        head() {
            return {
                title: 'Dad Jokes',
                meta: [{
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dada jokes'
                }]
            }
        },
        data() {
            return {
                jokes: []
            }
        },
        async created() {
            const config= {
                headers: {
                    Accept: 'application/json'
                }
            }
            try {
                const res = await axios.get('https://icanhazdadjoke.com/search', config)
                this.jokes = res.data.results
                console.log(this.jokes)
            } catch (e) {
                console.log(e)
            }
        },
        methods: {
            async searchText(text) {
                const config= {
                    headers: {
                        Accept: 'application/json'
                    }
                }
                try {
                    const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config)
                    this.jokes = res.data.results
                    console.log(this.jokes)
                } catch (e) {
                    console.log(e)
                }
            }
        }
    }
</script>

<style scoped>

</style>
