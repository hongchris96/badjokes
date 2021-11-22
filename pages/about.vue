<template>
    <div>
        <h1>Title of Bad Jokes</h1>
        <p>This is an app from a nuxtjs tutorial</p>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: 'About The App',
            meta: [
                {
                    hid: 'uniqueIdentifier',
                    name: 'actualMetaTag',
                    content: 'Some kind of content here that shows up in the head meta tag'
                },
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