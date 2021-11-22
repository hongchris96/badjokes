<template>
    <div>
        <!-- Loop thru for each joke in the array using v-for directive -->
        <!-- jokes array is in data() method -->
        <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
    </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke'

export default {
    components: {
        Joke
    },
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
            this.jokes = res.data.results; // stored in jokes array in data()
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