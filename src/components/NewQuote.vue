<template>
  <div class="row">
    <div class="col-sm-8 com-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
      <label for="textarea-quote">Quote</label>
      <textarea rows="3" v-model="quote" class="form-control" id="textarea-quote"></textarea>
    </div>
    <div class="col-sm-8 com-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
      <button class="btn btn-primary"
        @click.prevent="createNew"
      >Add new</button>
    </div>
  </div>

</template>

<script>
  export default {
    data: function () {
      return {
        quote: ""
      }
    },
    methods: {
      createNew: function () {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      }
    }
  }
</script>

<style>
</style>
