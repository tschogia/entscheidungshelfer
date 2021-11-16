<template>
  <v-app>
    <div>
    <h1>Willkommen beim Entscheidungshelfer!</h1>
    <v-btn class="text-button" to="/entscheidungshelfer">Entscheidungshelfer</v-btn>
    </div>
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

a {
  color: #42b983;
}
</style>
