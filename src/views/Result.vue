<template>


  <div id="result">
    <div>
      <h1>Ergebins:</h1>
      <br>
      <h2>Das Ergebnis ihrer Fragen ist: {{ summeCard }}</h2>
      <div class="center" style="margin-top: 1rem; margin-bottom: 1rem">
        - Ist Ihr Ergebnis kleiner oder gleich 12, wird Ihnen ein Mockup auf Papier empfohlen, <br>
        - Ist Ihr Ergebnis zwischen 13 und und 20, wird Ihnen ein Digitales Mockup tool empfohlen welches keine Interaktion bracht,<br>
        - Ist Ihr Ergebnis grösser als 20, wird ihnen ein Digitales Mockup Tool mit Interaktionsmöglichkeiten Entschieden.
      </div>
    </div>
    <div v-if="summeCard <= 12">
      <h2> Versuchen sie ein Mockup auf Papier zu erstellen um die ersten erfahrungen zu sammeln</h2>
      <img src="../assets/lofi-hifi-proto-sq-1024x1024.jpeg" alt="" style="margin-top: 2rem">
    </div>
    <div v-if="summeCard > 12 && summeCard < 20">
      <h2> Erstellen sie ein digitales Mockup ohne Interaktion</h2>
    </div>
    <div v-if="summeCard > 20">
      <h2> Erstellen sie ein digitales Mockup mit Interaktion</h2>
      <img src="../assets/05.jpeg" alt="" style="margin-top: 2rem">
    </div>
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

.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  text-align: left;
  width: 60%;
}

</style>
