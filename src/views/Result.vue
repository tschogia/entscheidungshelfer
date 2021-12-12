<template>


  <div id="result">
    <div>


      <h2 class="center" style="margin-top: 1rem; margin-bottom: 1rem">
        Das Fragen des Entscheidungshelfers sind in verschiedene Kategorien unterteilt und werden anhand der
        folgenden Präferenzmatrix gewichtet:
      </h2>
      <img src="../assets/Praeferenzmatrix.png" style="margin-top: 2rem">
    </div>
    <br>
    <v-btn class="text-button" @click="goto('h2')" style="margin-bottom: 2rem ">mehr Details</v-btn>
    <h1>Ergebins:</h1>
    <div v-if="summeCard <= 67">
      <h2> Versuchen sie ein Mockup auf Papier zu erstellen um die ersten erfahrungen zu sammeln</h2>
      <img src="../assets/lofi-hifi-proto-sq-1024x1024.jpeg" alt="" style="margin-top: 2rem">
    </div>
    <div v-if="summeCard > 67 && summeCard < 120">
      <h2> Erstellen sie ein digitales Mockup ohne Interaktion</h2>
      <div class="center" style="margin-top: 1rem; margin-bottom: 1rem">{{ descriptions[1].desctiption }}</div>

    </div>
    <div v-if="summeCard > 100">
      <h2> Erstellen sie ein digitales Mockup mit Interaktion</h2>
      <img src="../assets/05.jpeg" alt="" style="margin-top: 2rem">
    </div>
    <h2 ref="h2">Das Ergebnis ihrer Fragen ist: {{ summeCard }}</h2>
    <v-btn class="text-button" v-on:click="back" style="margin-bottom: 2rem; margin-top: 2rem"> Zurück zum Entscheidungshelfer</v-btn>
  </div>

</template>

<script>
import Card from "@/views/Card";
export default {
  comments: Card,
  methods: {
    goto(refName) {
      var element = this.$refs[refName];
      var top = element.offsetTop;

      window.scrollTo(0, top);
    },
    back() {
      this.$router.push({name: 'Entscheidungshelfer'});
    }
  },
    props: ['summeCard'],
    data() {
      return {
        name: "Result.vue",
        isclicked: false,
        results: [
          {result: "Papierform", answer: 0},
          {result: "Mockup ohne interaktion", answer: 0},
          {result: "Mockup mit Interaktion", answer: 0},
        ],
        descriptions: [
          {title: "Mockup / Wireframe auf Papier", desctiption: ""},
          {
            title: "diegitales statisches Mockup", desctiption: "Ein Digitales Mockup hat im Gegensatz " +
                "zur Papierform den Vorteil, dass mehrere Personen gleichzeitig daran arbeiten können. " +
                "Deshalb werden Mockups in Papierform meist nur verwendet, um eine grobe initiale Skize zu " +
                "erstellen welche später verwendet wird um daraus ein Statisches Mockup zu erstellen. Dabei ist " +
                "dem Benutzer überlassen in welchem detailierungsgrad das Mockup erstellt wird. Die erste Möglichkeit " +
                "ist ein Wireframe indem man nur die vorhandenen Funktionen darstellt und den Design Aspekt noch aussen " +
                "vor lässt. Bis hin zum vollständigen Design, welches den Stakeholdern oder gar den End Usern bereits gezeigt " +
                "werden kann um Feedback zu geben. "
          },
          {title: "diegitales interaktives Mockup", desctiption: ""}
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
  text-align: center;
  width: 50%;
}

</style>
