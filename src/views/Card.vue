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
          <v-card-title style="word-break: break-word;" class="text-center">{{ question.question }}</v-card-title>
          <v-card-actions class="justify-center">
          <v-radio-group row v-model="question.answer">
            <p class="label-left" >{{ question.min }}</p>
            <v-radio value="1">1</v-radio>
            <v-radio value="2">2</v-radio>
            <v-radio value="3">3</v-radio>
            <v-radio value="4">4</v-radio>
            <v-radio :label="question.max" value="5">5</v-radio>
          </v-radio-group>
          </v-card-actions>
<!--          <br>-->
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
        {question: "Wie viele Personen in ihrem Projekt arbeiten mit dem Mockup?",
          answer: 0,
          gewichtung: 2,
          min: "eine",
          max: "viele"
        },
        {question: "Werden im Projekt mehrere Personen gleichzeitig mit dem MockUp arbeiten?",
          answer: 0,
          gewichtung: 2,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "Arbeiten die Mitarbeiter des ganzen Projekts ortsunabhängig?",
          answer: 0,
          gewichtung: 2,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "Soll das MockUp verwendet werden, um eine durchgängige User Experience darzustellen?",
          answer: 0,
          gewichtung: 3,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "Soll das MockUp verwendet werden, um genaue Abläufe von technischen Funktionen der " +
              "Webseite (z.B. Filterfunktion, Suchfunktion, Darstellungsfunktionen etc.) zu detaillieren?",
          answer: 0,
          gewichtung: 3,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "Soll das erstellte MockUp verwendet werden, um Usertests durchzuführen?",
          answer: 0,
          gewichtung: 2,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "Welchen Detailierungsgrad wird mit dem MockUp in Hinblick zur endgültigen Lösung angestrebt?",
          answer: 0,
          gewichtung: 2,
          min: "simpel",
          max: "detailiert"
        },
        {question: "Wie wichtig beurteilen sie den Designe-Aspekt, des von ihnen angestrebten MockUps?",
          answer: 0,
          gewichtung: 1,
          min: "nicht relevant",
          max: "sehr relevant"
        },
        {question: "Wenn sie die Funktionalitäten und Umfang des User Interface betrachten, welches " +
              "mit dem MockUp dargestellt wird, wie komplex würden sie die Lösung beschrieben? ",
          answer: 0,
          gewichtung: 4,
          min: "nicht komplex",
          max: "sehr komplex"
        },
        {question: "Ist das Vorhaben starken zeitlichen Druck ausgesetzt?",
          answer: 0,
          gewichtung: 2,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "Ist das Vorhaben starken finanziellen Druck ausgesetzt?",
          answer: 0,
          gewichtung: 2,
          min: "eher nein",
          max: "eher ja"
        },
        {question: "in welcher Phase des Projekts befinden sie sich?",
          answer: 0,
          gewichtung: 2,
          min: "Entscheidungsfindung",
          max: "Detailiert Planung"
        }
      ]
    }
  },
  methods: {
    berechnen: function () {
      for (const q in this.questions) {
        this.summeAllerFragen = +this.summeAllerFragen + (+this.questions[q].answer * +this.questions[q].gewichtung);
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

.label-left {
  right: 0px;
  margin: auto;
  margin-right: 8px;
  vertical-align: middle;
  color: rgba(0, 0, 0, 0.6);
}


.text-center {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

</style>
