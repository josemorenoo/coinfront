<script setup>
import TableBar from './tablerow/TableBar.vue'
</script>

<template>
    <tr>
        <td v-for="column in columns" :key="column.key">
            <span v-if="column.key !== 'lines_of_code'">{{ entry[column.key] }}</span>
            <div v-if="column.key === 'lines_of_code'" class="bar" :style="{ width: barWidth + '%' }">
                <TableBar :barWidth="barWidth" :barValue="barValue" />
            </div>
        </td>
    </tr>
</template>

<script>

export default {
    props: {
        entry: Object,
        columns: Array,
        maxBarValue: Number
    },
    computed: {
        barValue() {
            return parseInt(this.entry.lines_of_code);
        },
        barWidth() {
            return (this.entry.lines_of_code / this.maxBarValue) * 100;
        },
    },
};
</script>

<style>
.row-text {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 32px;
    color: #F6F8FF;
}

.bar {
    background-color: #2CC3F3;
    border-radius: 34px;
    height: 25px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}
</style>