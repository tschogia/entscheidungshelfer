<template>
  <v-app>
    <v-container class="center">
      <h1>Entschteidungshelfer</h1>
      <br>
      <h3>Bitte füllen sie die Fragen so wahrtheitsgetrue wie möglich aus um ein zufriedenstellendes Ergebnis zu erhalten.</h3>
    </v-container>
    <v-container id="card">
      <v-flex v-for="question in questions" :key="question.question" class="card center">
        <v-card>
          <v-card-title class="text-center">{{ question.question }}</v-card-title>
          <v-form>
          <v-radio-group row v-model="question.answer" class="v-center">
            <v-radio label="1" value="1">1</v-radio>
            <v-radio label="2" value="2">2</v-radio>
            <v-radio label="3" value="3">3</v-radio>
            <v-radio label="4" value="4">4</v-radio>
            <v-radio label="5" value="5">5</v-radio>
          </v-radio-group>
          </v-form>
          <v-card-text>Ihre Antwort ist {{ question.answer }}</v-card-text>
        </v-card>
      </v-flex>

      <v-btn class="text-button" v-on:click="berechnen"> Berechnen</v-btn>
    </v-container>
  </v-app>
</template>

<script>
import Result from "@/views/Result.vue";

export default {
  comments: Result,
  props: ['summeCard'],
  data() {
    return {
      name: "Card.vue",
      isclicked: false,
      summeAllerFragen: 0,
      questions: [
        {question: "Wie gerne arbeiten sie am computer?", answer: 0},
        {question: "Wie oft brauchen sie mockups?", answer: 0},
        {question: "Wie viel erfahrung haben sie mit design oder mockup tools?", answer: 0},
        {question: "Wie fortgeschritten ist ihr projekt?", answer: 0},
        {question: "Wie gerne arbeiten sie mit menschen?", answer: 0},
        {question: "wkjksjfnschen?", answer: 0},
      ]
    }
  },
  methods: {
    berechnen: function () {
      for (const q in this.questions) {
        this.summeAllerFragen = +this.summeAllerFragen + +this.questions[q].answer;
      }
      this.$router.push({name: 'Result', params: { summeCard: this.summeAllerFragen } });
    }
  }
}
</script>

<style scoped>
.card {
  margin-top: 20px;
  width: 60%;
}

.text-button {
  text-align: center;
  margin-top: 30px;
  margin-bottom: 30px;
}

.flex-center {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 60%;
}

.v-center{
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}


.text-center {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

</style>
