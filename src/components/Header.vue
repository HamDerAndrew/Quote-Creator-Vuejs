<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes added</h3>
            <div class="progress">
                <div class="progress">
                    <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" v-bind:style="{width: (quoteCounter / maxQuotes) * 100 + '%'}"> 
                        {{ quoteCounter }} | {{ maxQuotes }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quoteCounter', 'maxQuotes']
}
</script>

<style>

</style>
