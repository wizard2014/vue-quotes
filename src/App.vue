<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quotes-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quotes-grid>

        <div class="row">
            <div class="col-sm-12">
                <div class="alert alert-info">
                    <p class="text-center">Click to the Quote to delete.</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import QuotesGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data() {
            return {
                quotes: [
                    'Just a Quote to see something'
                ],
                maxQuotes: 10
            };
        },
        components: {
            appQuotesGrid: QuotesGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        },
        methods: {
            newQuote(quote) {
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete Quotes first!');
                }

                this.quotes.push(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>
