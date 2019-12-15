<template>
  <div class="container">
    <hr>
    <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <new-quote @quoteAdded="quoteAdded"></new-quote>
    <quote-grid :quotes="quotes" @deletQuote="quoteDelete"></quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
          <div class="alert alert-info">
            Info: Click on a Quote to delete it!
          </div>
      </div>
    </div>
  </div>
</template>

<script>
import quoteGrid from './components/Quotes/QuoteGrid';
import newQuote from './components/Quotes/NewQuote';
import header from './components/Quotes/Progressbar';

export default {
  name: 'app',
  data(){
    return{
    quotes:[
      'just a new quote'
    ],
    maxQuotes:10
    }
  },
  components:{
    quoteGrid,
    newQuote,
    'appHeader':header
  },
  methods:{
    quoteAdded(quote){
      this.quotes.push(quote);
    },
    quoteDelete(index){
      this.quotes.splice(index,1);
    }
  }
}
</script>

<style>
.scontainer {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
