<template>
    <div>
                    <input type="text" :value=employee.id>
                    <input type="text" :value=employee.employee_name>
                    <input type="text" :value=employee.employee_age>
                    <input type="text" :value=employee.employee_salary>
                
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    props:{
        employee:{
            type: Object,
            default: {}
        }
    },
  
})
</script>

<style>

</style>