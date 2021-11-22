<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="text" placeholder="Search Jokes...">
        <input type="submit" value="Search Jokes">
    </form>
</template>

<script>
export default {
    name: 'SearchJokes',
    data() {
        return {
            text: ''
        }
    },
    methods: {
        onSubmit() {
            // filtering in vue, named search-text, payload this.text that was typed in
            this.$emit('search-text', this.text);
            this.text = "";
        }
    }
}
</script>

<style>

</style>