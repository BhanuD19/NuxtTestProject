<template>
  <div>
    <h1>About DadJokes</h1>
    <p>This is an app that displays corny dadJokes</p>
  </div>
</template>

<script>
    export default {
        name: "about",
        head() {
            return {
                title: 'About the app',
                meta: [{
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dada jokes'
                }]
            }

        }
    }
</script>

<style scoped>

</style>
