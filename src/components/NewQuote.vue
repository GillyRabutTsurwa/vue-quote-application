<template>
  <div class="row">
    <form action>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <!-- <label>Quote</label> -->
        <textarea
          rows="3"
          class="form-control"
          v-model="quote"
          v-on:keyup.enter="createNewQuote"
          placeholder="Enter Quote Here"
        ></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button v-on:click.prevent="createNewQuote" class="btn btn-primary">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
// import Quote from "./Quote";
export default {
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    createNewQuote() {
      // NOTE: SEND INFO FROM CHILD TO PARENT
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style lang="scss" scoped>
textarea {
  font-size: 1.8rem;
}

textarea:focus {
  box-shadow: inset 0 1px 1px rgba(212, 212, 212, 0.555),
    0 0 8px rgba(233, 233, 233, 0.904);
}
</style>
