<template>
    <div @click="removeQuote">
        <p>{{ quote.text }}</p>
    </div>
</template>

<script>
    export default {
        name: "Quote",
        props: ['quote'],
        methods: {
            removeQuote() {
                this.$emit('quoteWasRemoved', this.quote);
            }
        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css?family=Great+Vibes');

    div {
        border: 1px solid #ccc;
        border-radius: 5px;
        box-shadow: 1px 1px 2px black;
        padding: 20px;
        margin-right: 10px;
        margin-bottom: 10px;
        width: 22%;
        cursor: pointer;
    }

    div:hover {
        background-color: lightpink;
    }

    p {
        font-family: 'Great Vibes', cursive;
        font-size: 26px;
    }
</style>