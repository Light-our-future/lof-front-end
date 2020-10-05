<template>
    <div>
        <table>
            <tr>
                <td>
                    <input type="text" :value=employee.id>
                </td>
                <td>
                    <input type="text" :value=employee.employee_name>
                </td>
                <td>
                    <input type="text" :value=employee.employee_age>
                </td>
                <td>
                    <input type="text" :value=employee.employee_salary>
                </td>
                <td>
                    <!-- 여기서 못보내나? -->
                    <nuxt-link :to="'/employeeDetail/?employeeId=' + employee.id">detail</nuxt-link>
                    <!-- <nuxt-link to="/employeeDetail" :employeeId=employee.id>detail</nuxt-link> -->
                </td>
            </tr>
        </table>
    </div>
</template>


<script lang="ts">
import Vue from 'vue'


export default Vue.extend({
    props: {
        employee: {
            type: Object,
            required: true,
        },
    },
})
</script>