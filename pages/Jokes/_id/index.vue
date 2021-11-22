<template>
    <div>
        <nuxt-link to="/jokes">Back to Jokes</nuxt-link>
        <h3>{{ joke }}</h3>
        <hr />
        <small>Joke ID: {{ $route.params.id }}</small>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            joke: {}
        }
    },
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }
        try {
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
            console.log(res.data);
            this.joke = res.data.joke; // stored in joke in data()
        } catch (err) {
            console.log(err);
        }
    },
}
</script>

<style>

</style>