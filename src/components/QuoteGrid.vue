<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" :key="index" v-on:click.native="deleteTheQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    props: ['quotes'],
    components: {
        'app-quote': Quote
    },
    methods: {
        deleteTheQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    }
}
</script>

<style>

</style>
