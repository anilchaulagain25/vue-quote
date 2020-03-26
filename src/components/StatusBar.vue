<template>
  <div>
    <div class="progress top-buffer">
      <div
        class="progress-bar progress-bar-striped progress-bar-animated"
        role="progressbar"
        aria-valuenow="75"
        aria-valuemin="0"
        aria-valuemax="100"
        :style="{'width': quoteRatio+'%'}"
      >
        {{ quoteRatio }}%
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    quotes:{
      type:Array,
      required:true
    },
    maxNoOfQuotes:{
      type:Number,
      required:true
    }
  },
  computed:{
    quoteRatio:function(){
      return parseInt(this.quotes.length * 100 / this.maxNoOfQuotes)
    }
  }
}
</script>

<style>

</style>