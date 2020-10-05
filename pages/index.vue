<template>
  <div class="container">
    <Header />
    <EmployeeList
      :employeeList="employees"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '../components/Header.vue'
import EmployeeList from '../components/EmployeeList.vue'

interface Employee{
  id: Number,
  employee_name: String,
  employee_salary: String,
  employee_age: String,
  profile_image: String
}

export default Vue.extend({
  components:{
    Header,
    EmployeeList,
  },

  created(){
    this.employees = this.getEmployees()
  },
  // async created(){
  //   this.employees = await this.getEmployees()
  // },

  data:()=> ({
    employees: [] as Employee[]
  }),
  methods: {
    getEmployees(): Employee[]{
      const config = require('../test')
      return config.data
    }
    // async getEmployees(): Promise<Employee[]>{
    //   const config = await fetch("http://dummy.restapiexample.com/api/v1/employees")
    //     .then(config => config.json())
    //   return config
    // }
  }
  

})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
