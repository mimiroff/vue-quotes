<template>
    <div class="container">
        <appHeader></appHeader>
        <appProgressBar :quotesNumber="quotes.length" :quotesMax="quotesMax"></appProgressBar>
        <appNewQuote :quotesNumber="quotes.length" :quotesMax="quotesMax" @quoteWasAdded="addQuote"></appNewQuote>
        <div class="quote-container">
            <appQuote v-for="quote in quotes" :key="quote.id" :quote="quote" @quoteWasRemoved="removeQuote"></appQuote>
        </div>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import Footer from './components/Footer.vue';
    import NewQuote from './components/NewQuote.vue';
    import Quote from './components/Quote.vue';
    import ProgressBar from './components/ProgressBar.vue';

    export default {
        components: {
            appHeader: Header,
            appFooter: Footer,
            appNewQuote: NewQuote,
            appQuote: Quote,
            appProgressBar: ProgressBar
        },
        data() {
            return {
                quotes: [],
                quotesMax: 3
            }
        },
        methods: {
            removeQuote(quote) {
                this.quotes = this.quotes.filter((el) => {
                    if (el.id !== quote.id) {
                        return el;
                    }
                });
            },
            addQuote(quote) {
                this.quotes.push(quote);
                
            }
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
