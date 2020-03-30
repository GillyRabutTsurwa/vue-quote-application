<template>
  <div id="container">
    <img src="./assets/logo.png" class="vue-logo" alt="Vue logo" />
    <!-- NOTE:IMPORANT: $event = this.quote in NewQuote -->
    <Header v-bind:quoteCountProp="quotes.length" v-bind:maxQuotesProp="maxQuotes"></Header>
    <NewQuote v-on:quoteAdded="newQuote($event)"></NewQuote>
    <QuoteGrid :quotesProp="quotes" v-on:quoteDeleted="deleteMyQuote($event)"></QuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a quote to delete</div>
      </div>
    </div>
    <img src="./assets/trollface.png" class="troll-face" alt="asdfasd" />
  </div>
</template>

<script>
import Header from "./components/Header";
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
export default {
  data() {
    return {
      quotes: ["Juste pour voir qq'chose"],
      maxQuotes: 10
    };
  },
  components: {
    QuoteGrid: QuoteGrid,
    NewQuote: NewQuote,
    Header: Header
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length < this.maxQuotes) {
        this.quotes.push(quote);
      } else {
        return alert("Please delete quotes before adding new ones");
      }
    },
    deleteMyQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Comic+Neue:400,700&display=swap");
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
#container {
  position: relative;
  padding: 0 2rem;
  background-color: #2c3e50;
  color: #fff;
  min-height: 100vh;
}

.vue-logo {
  position: absolute;
  top: 2em;
  left: 2em;
  height: 2em;
}

.troll-face {
  position: absolute;
  height: 2.5rem;
  bottom: 1.5rem;
  right: 1.5rem;
}
</style>
