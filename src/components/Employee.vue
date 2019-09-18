<template>
  <div class='column'>
    <div class='card equal-height'>
      <div class='card-content is-flex-reverse is-horizontal-center'>
        <div>
          <h1><strong>Nombre:</strong> {{ name }}</h1><br/>
        </div>
        <div>
          <h1><strong>Apellido:</strong> {{ lname }}</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Employee',
  props: {
    name: String,
    lname: String,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  margin-top: 10px;
}
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
</style>
