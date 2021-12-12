<template>


  <div id="result">
    <h1>Ergebnis:</h1>
    <div v-if="summeCard <= 25">
      <h2> Versuchen sie ein Mockup auf Papier zu erstellen um die ersten erfahrungen zu sammeln</h2>
      <div class="center" style="margin-top: 1rem; margin-bottom: 1rem">
        {{ descriptions[0].desctiption }}
        <br>
        <br>
        <div style="font-weight: bold"> Als Gedankenstütze: Ein Wirframe sollte die folgenden Punkte abbilden:<br></div>
        - Die Hauptelemente der Inhalte (Was?)<br>
        - Die Struktur der Informationen (Wo?)<br>
        - Eine Beschreibung und grundlegende Visualisierung der Benutzerschnittstelle (Wie?)
      </div>
      <img src="../assets/die-besten-wireframe-tools.jpg" alt="" style="margin-top: 2rem">
    </div>
    <div v-if="summeCard > 25 && summeCard < 35">
      <h2> Erstellen sie ein digitales Mockup ohne Interaktion</h2>
      <div class="center" style="margin-top: 1rem; margin-bottom: 1rem">{{ descriptions[1].desctiption }}</div>
      <img src="../assets/walling-2-a9wDBS1KE-unsplash.jpg" alt="" style="margin-top: 2rem; width: 60%">
    </div>
    <div v-if="summeCard > 35">
      <h2> Erstellen sie ein digitales Mockup mit Interaktion</h2>
      <div class="center" style="margin-top: 1rem; margin-bottom: 1rem">{{ descriptions[2].desctiption }}</div>
      <img src="../assets/05.jpeg" alt="" style="margin-top: 2rem">
    </div>
    <br>
    <h2>Details zur Entscheidung:</h2>
    <div>
      <h2 class="center" style="margin-top: 1rem; margin-bottom: 1rem">
        Das Fragen des Entscheidungshelfers sind in verschiedene Kategorien unterteilt und werden anhand der
        folgenden Präferenzmatrix gewichtet:
      </h2>
      <img src="../assets/Praeferenzmatrix.png" style="margin-top: 2rem">
    </div>
   <!-- <h2 ref="h2">Das Ergebnis ihrer Fragen ist: {{ summeCard }}</h2> -->
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
      window.scrollTo(0,0);
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
          {title: "Mockup / Wireframe auf Papier", desctiption: "Aufgrund deiner Antworten empfehlen wir " +
                "dir das Arbeiten mit Handskizzen und statischen Wireframes. Die dadurch erhaltene Repräsentation " +
                "des Designs und Darstellung der verwendeten Positionierung und Grösse der Elemente ist für dein Projekt ausreichend. " +
                "Fokussiere dich auf die einzelnen Elemente der späteren Seite, diese innerhalb des Layouts anzuordnen und nicht ein " +
                "finales Design der Webseite jetzt zu spezifizieren."
                },
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
          {title: "diegitales interaktives Mockup", desctiption: "Durch die von Ihnen bereitgestellten Informationen, " +
                "schlägt der Entscheidungshelfer die Erstellung eines interaktiven Mockups vor. " +
                "Interaktivität bedeutet, dass mit Ihrem Mockup interagiert werden kann. " +
                "Beispielsweise wird mit einem Klick auf einen Button eine neue Seite geöffnet. " +
                "Interaktivität muss jedoch nicht immer auch High-Fidelity, aslo eine hohe Wiedergabetreue, " +
                "bedeuten. Interaktivität lässt sich heutzutage mit beinahe allen gängigen Mockup-Tools integrieren. " +
                "Ein Beispiel für ein Interaktives Low-Fidelity Tool ist Balsamiq. Wird jedoch High-Fidelity gewünscht, " +
                "so sind andere Tools wie beispielsweise Axure oder Adobe XD zu empfehlen."}
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
  text-align: justify;
  width: 50%;
  font-size: 21px;
}

</style>
