<template>
  <div class="container">
    <div class="row">
  <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
  <new-quote @quoteAdded="newQuote"></new-quote> /* event listeners - quoteAdded */
    <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid> /* event listeners - quoteDeleted */

    <div class="col-sm-12 text-center">
      <div class="alert alert-info">Info! Click Quotes to delete it respectively</div>
    </div>
    </div>
  </div>
</template>

<script>

  import Quotegrid from './components/Qoutegrid.vue';
  import Newquote from './components/Newquote.vue';
  import header from './components/header.vue';
    export default {
      data : function(){
          return{
              quotes:['Just a Qoute to see something'],
              maxQuotes:10
          }
      },
      methods : {
          newQuote(quote) {
              this.quotes.push(quote);
          },
          deleteQuote(index){
              this.quotes.splice(index,1);
          }
      },
      components:{
          quoteGrid : Quotegrid,
          newQuote : Newquote,
          appHeader : header
      }
    }
</script>

<style>
</style>
