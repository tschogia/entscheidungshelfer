<template>
  <v-container>
    <v-flex v-for="question in questions" :key="question.question">
      <v-card>
        <v-card-title>{{ question.question }}</v-card-title>
        <v-radio-group v-model="question.answer">
          <v-radio label="1" value="1">1</v-radio>
          <v-radio label="2" value="2">2</v-radio>
          <v-radio label="3" value="3">3</v-radio>
          <v-radio label="4" value="4">4</v-radio>
        </v-radio-group>
        <v-card-text>Ihre Antwort ist {{ question.answer }}</v-card-text>
      </v-card>
    </v-flex>
  </v-container>

</template>

<script>
export default {
  data() {
    return {
      name: "Card.vue",
      questions: [
        {question: "wie gerne arbeiten sie am computer?", answer: 0},
        {question: "wie oft brauchen sie mockups?", answer: 0},
        {question: "wie viel erfahrung haben sie mit design oder mockup tools?", answer: 0},
        {question: "wie fortgeschritten ist ihr projekt?", answer: 0},
        {question: "wie gerne arbeiten sie mit menschen?", answer: 0},
      ],
      q1: 0,
      q2: 0,
      q3: 0,
      q4: 0,
      q5: 0
    }
  }
}
</script>

<style scoped>

</style>
