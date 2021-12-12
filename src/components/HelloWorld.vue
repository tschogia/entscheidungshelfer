<template>
  <v-app>
    <v-container>
    <div>
      <h1>Herzlich Willkommen beim Mockup-Entscheidungshelfer!</h1>
      <br>
      <div class="center">
        Gerne möchten wir Ihnen mehr über uns,
        sowie den Entscheidungshelfer selber erzählen.
        <br>
        <br>
        Wir sind 3 Studierende im Studiengang Wirtschaftsinformatik an der Zürcher Hochschule für angewandte Wissenschaften.
        Im Modul «Integration» haben wir uns für die Aufgabe entschieden, den Unterschied zwischen verschiedenen
        Mockup-Tools genauer zu analysieren und aufgrund diesen Analysen einen Entscheidungshelfer zu programmieren,
        welcher die Wahl eines Mockup-Tools erleichtern soll.
        <br>
        <br>
        In diesem Entscheidungshelfer werden Ihnen diverse Fragen zu Ihrem Projekt gestellt.
        Im Hintergrund wird dann aufgrund dieser Fragen eine Empfehlung für sie berechnet und anschliessend vorgeschlagen.
        Das Ergebnis soll Aufschluss darüber geben, wie Sie ihr Mockup am besten erstellen,
        ob beispielsweise per Hand, statisch oder interakitv.
      </div>
      <v-btn class="text-button" to="/entscheidungshelfer">Entscheidungshelfer</v-btn>
      <img src="../assets/entschidungshelfer.jpeg" alt="" class="center" style="margin-top: 2rem">
    </div>
    </v-container>
  </v-app>
</template>

<script>
import router from "@/router";

export default {
  data() {
    return {
      name: 'HelloWorld',
      msg: String,
    }
  },
  methods: {
    toentscheidungshelfer: function () {
      router.go("/entscheidungshelfer")
    }
  }

}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

.text-button {
  text-align: center;
  margin-top: 30px;
  margin-bottom: 30px;
}

.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 60%;
  text-align: justify;
  font-size: 21px;
}

a {
  color: #42b983;
}
</style>
