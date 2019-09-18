<template>
  <div id="app" class="container">
    <div class='card-content is-flex is-horizontal-center'>
      <figure class="image is-128x128">
        <img src="https://avatars2.githubusercontent.com/u/28398930?s=200&v=4">
      </figure>
    </div>
    <div id="employees" v-for="employee in employees" :key="employee.id">
      <Employee :name=employee.name :lname=employee.lname />
    </div>
  </div>
</template>

<script>
import Employee from './components/Employee.vue'
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Employee,
  },
  data() {
    return {
      employees: [],
    }
  },
  methods: {
    fetchEmployees() {
      axios.get('http://local.softon-apps.com:8000/employees')
        .then(response => {
          this.employees = response.data
        })
        .catch(() => {
        })
        .finally(() => {
        })
    }
  },
  mounted() {
    this.fetchEmployees()
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.is-horizontal-center {
  justify-content: center;
}
</style>
