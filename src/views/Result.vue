<template>


  <div id="result">
    <h1>Ergebnis:</h1>
    <div v-if="summeCard <= 25">
      <h2> Versuchen sie ein Mockup auf Papier zu erstellen</h2>
      <div class="center-left" style="margin-top: 1rem; margin-bottom: 1rem">
        <div style="text-align: justify">{{ descriptions[0].desctiption }}</div>
        <br>
        <div style="font-weight: bold; text-align: left;"> Als Gedankenstütze: Ein Wireframe sollte die folgenden Punkte abbilden:<br></div>
        <div style="text-align: left">
        - Die Hauptelemente der Inhalte (Was?)<br>
        - Die Struktur der Informationen (Wo?)<br>
        - Eine Beschreibung und grundlegende Visualisierung der Benutzerschnittstelle (Wie?)
        </div>
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
      <img src="../assets/Matrix.png" style="margin-top: 2rem; margin-bottom: 2rem">

    </div>
    <div class="center-left" style="text-align: left">

      1 -	Wie viele Personen in ihrem Projekt arbeitet mit dem MockUp?<br>
      2 -	Werden im Projekt mehrere Personen gleichzeitig mit dem MockZup arebiten<br>
      3 -	Arbeiten die Mitarbeiter des ganzen Projekts am gleichen Ort oder ortsunabhängig<br>
      4 -	Soll das MockUp verwendet werden, um eine durchgängige User Experience darzustellen?<br>
      5 -	Soll das MockUp verwendet werden um genaue Abläufe von technischen Funktionen der Webseite (z.B. Filterfunktion, Suchfunktion, Darstellungsfunktionen etc. zu detaillieren?<br>
      6 -	Soll das erstellte MockUp verwendet werden, um Usertests durchzuführen?<br>
      7 -	Welchen Detailierungsgrad wird mit dem MockUp hinsichtlich der endgültigen Lösung angestrebt?<br>
      8 -	In welcher Phase des Projekts befinden sie sich?<br>
      9 -	Soll das MockUp verwendet werden, um zu prüfen, on echte Nutzer das Tool intuitiv verstehen?<br>
      10 -	Wie wichtig beurteilen sie den Design-Aspekt, des von ihnen angestrebten MockUp’s?<br>
      11 -	Wenn sie die Funktionalität und Umfang des User Interface betrachten, welches mit dem MockUp dargestellt wird, wie komplex würden sie die Lösung beschreiben?<br>
      12 -	Ist das Vorhaben starkem zeitlichen Druck ausgesetzt?<br>
      13 -	Ist das Vorhaben starkem finanziellen Druck ausgesetzt?<br>

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
                "ihnen das Arbeiten mit Handskizzen und statischen Wireframes. Die dadurch erhaltene Repräsentation " +
                "des Designs und Darstellung der verwendeten Positionierung und Grösse der Elemente ist für dein Projekt ausreichend. " +
                "Fokussiere dich auf die einzelnen Elemente der späteren Seite, diese innerhalb des Layouts anzuordnen und nicht ein " +
                "finales Design der Webseite jetzt zu spezifizieren."
                },
          {
            title: "diegitales statisches Mockup", desctiption: "Ein Digitales Mockup hat im Gegensatz " +
                "zur Papierform den Vorteil, dass mehrere Personen gleichzeitig daran arbeiten können. " +
                "Deshalb werden Mockups in Papierform meist nur verwendet, um eine grobe initiale Skizze zu " +
                "erstellen welche später verwendet wird um daraus ein Statisches Mockup zu erstellen. Dabei ist " +
                "dem Benutzer überlassen in welchem detaillierungsgrad das Mockup erstellt wird. Die erste Möglichkeit " +
                "ist ein Wireframe indem man nur die vorhandenen Funktionen darstellt und den Design Aspekt noch aussen " +
                "vor lässt. Bis hin zum vollständigen Design, welches den Stakeholdern oder gar den End Usern bereits gezeigt " +
                "werden kann um Feedback zu geben. "
          },
          {title: "diegitales interaktives Mockup", desctiption: "Durch die von Ihnen bereitgestellten Informationen, " +
                "schlägt der Entscheidungshelfer die Erstellung eines interaktiven Mockups vor. " +
                "Interaktivität bedeutet, dass mit Ihrem Mockup interagiert werden kann. " +
                "Beispielsweise wird mit einem Klick auf einen Button eine neue Seite geöffnet. " +
                "Interaktivität muss jedoch nicht immer auch High-Fidelity, also eine hohe Wiedergabetreue " +
                "bedeuten. Interaktivität lässt sich mit beinahe allen gängigen Mockup-Tools integrieren. " +
                "Ein Beispiel für ein interaktives Low-Fidelity Tool ist Balsamiq. Wird jedoch High-Fidelity gewünscht, " +
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

.center-left {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 60%;
  font-size: 21px;
}

</style>
