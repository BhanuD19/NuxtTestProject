<template>
    <form @submit.prevent="OnSubmit">
      <input type="text" v-model="text" placeholder="Search jokes">
      <input type="submit" value="Search Jokes">
    </form>
</template>

<script>
    export default {
        name: "SearchJokes",
        data() {
            return {
                text: ''
            }
        },
        methods: {
            OnSubmit() {
                this.$emit('search-text', this.text)
                this.text= ''
            }
        }
    }
</script>

<style scoped>

</style>
