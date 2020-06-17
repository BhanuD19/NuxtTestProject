<template>
    <div>
      <nuxt-link to="/jokes">Back to jokes</nuxt-link>
      <h2>{{ joke }}</h2>
      <hr />
      <small>Joke Id: {{ $route.params.id }}</small>
    </div>
</template>

<script>
  import axios from 'axios'
    export default {
        name: "index",
        data() {
            return {
                joke: {}
            }
        },
        head() {
            return {
                title: this.joke,
                meta: [{
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dada jokes'
                }]
            }
        },
        async created() {
            const config= {
                headers: {
                    Accept: 'application/json'
                }
            }
            try {
                const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
                this.joke = res.data.joke
            } catch (e) {
                console.log(e)
            }
        }
    }
</script>

<style scoped>

</style>
