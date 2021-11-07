<template>
  <div class="header">
    {{ title }}
  </div>
</template>

<script>
export default {
  data() {
    return {
        title: 'Entscheidungshelfer'
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
a {
  color: #42b983;
}
.header {
  width: 100%;
  padding: 15px 10%;
  background: darkblue;
  color: white;
  position: sticky; top: 0;
}
</style>
