<template>
  <div class="row">
    <Quote
      v-for="(currentQuote, index) in quotesProp"
      v-bind:key="index"
      v-on:click.native="deleteQuote(index)"
    >{{currentQuote}}</Quote>
  </div>
</template>

<script>
import Quote from "./Quote";
export default {
  props: {
    quotesProp: Array
  },
  components: {
    Quote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>

<style scoped>
</style>