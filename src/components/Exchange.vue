<template>
  <div class="exchange">
    <h1 class="title">{{ msg }}</h1>
    <div class="result-area">
      <div v-if="data.result != 'error'">
        <div class="result">
          1&#36; = {{ data.rates.EUR }} <span class="currency">&#8364;</span>
        </div>
        <div class="result">
          1&#36; = {{ data.rates.TRY }} <span class="currency">&#8378;</span>
        </div>
      </div>
      <div v-else>
        A problem occurred
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Exchange",
  props: {
    msg: String,
    data: Object
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title{
  margin-bottom: 1em;
  color: #a2bddf;
}
.result{
  margin-bottom: .5em;
  font-size: 30px;
}
</style>
