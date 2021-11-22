<template>
    <div>
        <!-- onSubmit form -->
        <form @submit.prevent="onSubmit">
            <input type="text" v-model="onSubmitText" placeholder="Search Jokes on submit...">
            <input type="submit" value="Search Jokes">
        </form>

        <!-- onChange input -->
        <form @submit.prevent="clearText">
            <input type="text" v-model="onChangeText" placeholder="Search Jokes on change..." @input="onChange">
            <input type="submit" value="Clear">
        </form>
    </div>
</template>

<script>
export default {
    name: 'SearchJokes',
    data() {
        return {
            onSubmitText: '',
            onChangeText: ''
        }
    },
    methods: {
        onSubmit() {
            // filtering in vue, named search-text, payload this.text that was typed in
            this.$emit('search-text', this.onSubmitText);
            this.onSubmitText = "";
        },
        onChange() {
            this.$emit('change-text', this.onChangeText);
        },
        clearText() {
            this.$emit('clear-text');
            this.onChangeText = "";
        }
    }
}
</script>

<style>

</style>