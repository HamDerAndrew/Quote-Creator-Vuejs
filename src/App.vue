<template>
    <div class="container">
        <app-header v-bind:quoteCounter="quotes.length" v-bind:maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteSubmit = "quoteInsert"></app-new-quote>
        <app-quote-grid v-bind:quotes = "quotes" @quoteDeleted="deleteTheQuote"></app-quote-grid>
        <div class="div row">
            <div class="div col-sm-12 text-center">
                <div class="alert alert-success">
                    <p> Click on a quote in order to delete it</p>
                </div>
                <div class="alert alert-danger">
                    <p> This app was created by learning from Maximilian Schwarzmüller</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Quote from './components/Quote.vue';
import Header from './components/Header.vue';
    export default {
        data() {
            return {
                maxQuotes: 10,
                quotes: ['My quote']
            };
        },
        methods: {
            quoteInsert(quote) {
                if(this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete quote before adding a new one');
                }
                this.quotes.push(quote);
            },
            deleteTheQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            'app-quote-grid': QuoteGrid,
            'app-quote': Quote,
            'app-new-quote': NewQuote,
            'app-header': Header
        }
    }
</script>

<style>
</style>
