<template>
    <div>
        <h3>Quote</h3>
        <textarea name="newQuote" id="newQuote" cols="100" rows="3" v-model="qoute.text"></textarea>
        <button @click="addQuote">Add Quote</button>
    </div>

</template>

<script>
    export default {
        name: "NewQuote",
        props: {
            quotesNumber: Number,
            quotesMax: Number
        },
        computed: {
            newQuoteId() {
                return this.quotesNumber + 1;
            },
            qoute() {
                return {
                    id: this.newQuoteId,
                    text: ''
                }
            }
        },
        methods: {
            addQuote() {
                if(this.quotesNumber < this.quotesMax) {
                    this.$emit('quoteWasAdded', this.qoute);
                }
            }
        }
    }
</script>

<style scoped>
    div {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 60%;
        margin: auto;
    }

    button {
        padding: 10px 15px;
        border: 1px solid #46b8da;
        border-radius: 5px;
        color: #fff;
        background-color: #46b8da;
        margin-top: 10px;
        font-size: 16px;
    }

    button:hover {
        background-color: royalblue;
    }

    button:active {
        box-shadow: inset 2px 2px 2px darkblue;
        outline: none;
    }

    button:focus {
        outline: none;
    }

    h3 {
        align-self: flex-start;
        font-size: 18px;
        font-weight: bold;
    }

    textarea {
        width: 100%;
        height: 80px;
        border-radius: 5px;
    }
</style>