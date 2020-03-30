<template>
  <div class="row">
    <h1 class="title">Quote-Saver</h1>
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress">
          <div
            class="progress-bar"
            role="progressbar"
            aria-valuenow="60"
            aria-valuemin="0"
            aria-valuemax="100"
            v-bind:style="{width: (quoteCountProp / maxQuotesProp) * 100 + '%'}"
          >
            <span v-if="quoteCountProp > 0">{{quoteCountProp}} / {{maxQuotesProp}}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quoteCountProp: Number,
    maxQuotesProp: Number
  }
};
</script>

<style scoped>
.title {
  text-align: center;
  font-size: 3.5em;
}

.progress-bar {
  text-align: center;
  font-size: 1.5rem;
}
</style>