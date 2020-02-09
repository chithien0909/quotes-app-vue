<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress">
          <div
            :aria-valuenow="(quoteCount / maxQuotes) * 100"
            aria-valuemin="0"
            aria-valuemax="100"
            class="progress-bar" role="progressbar"
            :style="{width: (quoteCount / maxQuotes) * 100 + '%'}"
          >
              {{ quoteCount }} / {{ maxQuotes}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    props: {
      quoteCount: {
        type: Number
      },
      maxQuotes: {
        type: Number
      }
    }
  }
</script>
