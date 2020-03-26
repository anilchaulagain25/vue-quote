<template>
  <div class="container">
    <StatusBar
      :quotes="quotes"
      :max-no-of-quotes="maxNoOfQuotes"
    />
    <AddQuote @addQuote="addQuote($event.value)" />
    <QuoteGrid
      :quotes="quotes"
      @removeQuote="removeQuote($event.index)"
    />
  </div>
</template>

<script>
import StatusBar from './components/StatusBar'
import AddQuote from './components/AddQuote'
import QuoteGrid from './components/QuoteGrid'
export default {
  name: 'App',
  components: {
    StatusBar,
    AddQuote,
    QuoteGrid
  },
  data(){
    return{
      quotes:['This is default quote','This is second default'],
      maxNoOfQuotes:10
    }
  },
  methods:{
    addQuote:function (value) {
      if(this.maxNoOfQuotes === this.quotes.length)
          {
            alert(`Max allowed no. of quotes are ${this.maxNoOfQuotes}`);
          }
          else if(value){
            this.quotes.push(value)
          } 
    },
    removeQuote(index){
      this.quotes.splice(index,1);
    }
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.top-buffer{
  margin-top:10px;
}
</style>
