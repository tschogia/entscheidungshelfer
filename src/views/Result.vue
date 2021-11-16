<template>
  <div id="result">

    <h1> Das ergebnis ihrer umfrage ist die {{ summeCard }}</h1>
  </div>
</template>

<script>
import Card from "@/views/Card";
export default {
  comments: Card,
  props: ['summeCard'],
  data() {
    return {
      name: "Result.vue",
      isclicked: false,
      results: [
        {result: "Papierform", answer: 0},
        {result: "Mockup ohne interaktion", answer: 0},
        {result: "Mockup mit Interaktion", answer: 0},
      ]
    }
  }
}
</script>

<style scoped>

</style>
