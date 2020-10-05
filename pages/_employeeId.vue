<template>
    <div>
        <EmployeeDetail
            :employee="employee"
        />
    </div>
</template>

<script lang='ts'>
import Vue from 'vue'
import EmployeeDetail from '../components/EmployeeDetail.vue'

interface Employee{
  id: Number
  employee_name: String
  employee_salary: String
  employee_age: String
  profile_image: String
}

export default Vue.extend({
    components:{
        EmployeeDetail,
    },
    props: {
        employeeId: {
            type: Number,
            default: 0,
        }
    },
    created() {
        this.employee = this.getEmployeeDetail(this.employeeId)
        console.log(this.employeeId)
    },
    data:()=> ({
        employee: {} as Employee,
    }),
    methods:{
        getEmployeeDetail(employeeId: Number): Employee {
            const json = require('../test')
            const employeeDetailList:Employee[] = json.data
            console.log(employeeId)
            let test:Employee = {id: 0, employee_name: "test", employee_salary: "", employee_age: "", profile_image:""}

            for(var employee of employeeDetailList){
                if(employee && employee.id == employeeId){
                    test = employee
                }
            }

            return test
        }
    }

})
</script>