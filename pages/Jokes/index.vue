<template>
    <div>jokes</div>
</template>

<script>
import axios from 'axios';

export default {
    // Returning object with data
    data() {
        return {
            jokes: []
        }
    },
    // For request to run as soon as components load, use lifecycle method created()
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }
        try {
            const res = await axios.get('https://icanhazdadjoke.com/search', config);
            console.log(res.data);
            this.jokes = res.data.results;
        } catch (err) {
            console.log(err);
        }
    },
    head() {
        return {
            title: 'Bad Jokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Pool of bad jokes'
                }
            ]
        }
    }
}
</script>

<style>

</style>