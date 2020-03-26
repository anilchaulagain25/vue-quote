<template>
  <div class="row top-buffer">
    <div
      v-for="(quote,index) in quotes"
      :key="quote"
      class="col-4 quote-block"
      @click="$emit('removeQuote',{index:index})"
    >
      {{ quote }}
    </div>
  </div>
</template>

<script>

export default {
  props:{
    quotes:{
      type:Array,
      required:true
    }
  }
}
</script>

<style scoped>
@import 'https://fonts.googleapis.com/css?family=Liu+Jian+Mao+Cao&display=swap';
.quote-block{
  border: 1px solid black;
  margin: 2px;
  border-radius: 5px;
  font-family: 'Liu Jian Mao Cao', cursive;
  font-size: 25px;
  
}
</style>