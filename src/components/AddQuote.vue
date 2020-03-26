<template>
  <div>
    <div class="row top-buffer">
      <div class="col-md-6">
        <textarea
          v-model="quote"
          class="form-control"
          cols="10"
          rows="5"
        />
      </div>
      <div class="col-md-2">
        <button
          class="btn btn-info"
          :disabled="isValidQuote===false"
          @click="addQuote"
        >
          Add
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            quote:''
        }
    },
    computed:{
      isValidQuote:function(){
        return this.quote !== ''
      }
    },
    methods:{
        addQuote(){
          
            this.$emit('addQuote',{value:this.quote});
            this.quote='';
        }
    }
}
</script>

<style>

</style>