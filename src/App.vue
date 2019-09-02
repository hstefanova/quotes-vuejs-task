<template>
  <div class="container">
    <ProgressBar 
      :quoteCount="quotes.length" 
      :maxQuotes="maxQuotes"
    ></ProgressBar>

    <InputQuote @quoteCreated="addQuote"></InputQuote>
    
    <QuoteGrid @quoteDeleted="removeQuote" :quotes="quotes"></QuoteGrid>

    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a Quote to delete it.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
    import InputQuote from './components/InputQuote.vue'
    import QuoteGrid from './components/QuoteGrid.vue'
    import ProgressBar from './components/ProgressBar.vue'

    export default {
        data: function() {
        return {
            quotes: ['Just a Quote to see something'],
            maxQuotes: 5
          }
        },
        methods: {
          addQuote(quote) {
            if(this.quotes.length >= this.maxQuotes) {
              alert('Please delete quotes first!')
            }
            this.quotes.push(quote);
            this.quote = '';
            
          },
          removeQuote(index) {
            this.quotes.splice(index, 1)
          }
        },
        components: {
            QuoteGrid: QuoteGrid,
            InputQuote: InputQuote,
            ProgressBar: ProgressBar
        }
    }
</script>

<style></style>