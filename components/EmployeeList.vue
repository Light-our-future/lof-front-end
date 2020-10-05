<template>
    <div>
        <Employee
            v-for="employee in employeeList" :key="employee.id"
            :employee="employee"
        />
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Employee from './Employee.vue'


export default Vue.extend({
    components: {
        Employee,
    },
    props: {
        employeeList: {
            type: Array,
            default: [],
        },
    },
    created() {
        console.log(typeof this.employeeList)
    }
})
</script>