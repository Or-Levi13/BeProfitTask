<template>
    <v-table>
        <thead>
            <tr>
                <th v-for="header in tableHeaders" :key="header" class="text-left">
                    {{ header }}
                </th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="item in desserts" :key="item.name">
                <td>{{ item.order_ID }}</td>
                <td>{{ item.name }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                <td>{{ item.total_refunded }}</td>
                
            </tr>
        </tbody>
    </v-table>
    <div class="text-center">
        <v-pagination v-model="page" :length="6"></v-pagination>
    </div>
</template>

<script lang="ts">
import ordersData from '@/data/orders.json';

export default {
    created() {
        console.log(ordersData.map(item => Object.keys(item))[0]);
        this.tableHeaders = ordersData.map(item => Object.keys(item))[0].map(item => this.capitalizeFirstLetter(item.replace(/_/g, ' ')));
    },
    data() {
        return {
            tableHeaders: [""],
            page: 1,
            desserts: ordersData,
        }
    },
    methods: {
        capitalizeFirstLetter(string: String) {
            return string.charAt(0).toUpperCase() + string.slice(1);
        }
    }
}
</script>
<style lang="">
    
</style>