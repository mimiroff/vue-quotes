<template>
    <div class="container">
        <appHeader></appHeader>
        <appProgressBar></appProgressBar>
        <appNewQuote></appNewQuote>
        <div class="quote-container">
            <appQuote></appQuote>
            <appQuote></appQuote>
            <appQuote></appQuote>
            <appQuote></appQuote>
            <appQuote></appQuote>
            <appQuote></appQuote>
        </div>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import Footer from './components/Footer.vue';
    import NewQuote from './components/NewQuote.vue';
    import Quote from './components/Quote.vue';
    import ProgressBar from './components/ProgressBar.vue'

    export default {
        components: {
            appHeader: Header,
            appFooter: Footer,
            appNewQuote: NewQuote,
            appQuote: Quote,
            appProgressBar: ProgressBar
        }
    }
</script>

<style scoped>
    .quote-container {
        display: flex;
        flex-wrap: wrap;
        margin-top: 10px;
    }
</style>
