<template>
  <div id="container">
    <app-header
      :maxQuotes="maxQuotes"
      :quoteCount="quotes.length"
    />
    <app-new-quote
      @quoteAdded="newQuote"
    />
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
    />

    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a Quote to delete it
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid';
  import NewQuote from './components/NewQuote';
  import Header from './components/Header';
  export default {
    data: function () {
      return {

        maxQuotes: 10,
        quotes: [
          'Just a Quote to see something',

        ],
        currentId: 2,
      }
    },
    components: {
      appNewQuote: NewQuote,
      appQuoteGrid: QuoteGrid,
      appHeader: Header,
    },
    methods: {
      newQuote: function (quote) {
        if(this.quotes.length >= this.maxQuotes ) {
          return alert('Please delete a quote first')
        }
        this.quotes.push(quote);
      },
      deleteQuote: function (index) {
        this.quotes.splice(index, 1);
      }
    }
  }
</script>

