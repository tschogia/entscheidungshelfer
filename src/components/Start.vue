<template>
  <div v-if="startFlag">
    <h1>willkommen bei unserem entscheidungshelfer</h1>
    <button v-on:click="weiter"> weiter</button>

  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Start.vue",
      startFlag: true
    }
  },
  methods: {
    weiter: function () {
      this.startFlag = false;
      console.log("weiter is triggered")
    }
  }
}
</script>

<style scoped>

</style>
