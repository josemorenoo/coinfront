<script setup>
import RowBar from './tablerow/RowBar.vue'
import RowPrice from './tablerow/RowPrice.vue'
import RowLogoAndName from './tablerow/RowLogoAndName.vue';
</script>

<template>
    <tr class="table-row">
        <td v-for="column in columns" :key="column.key">
            <div v-if="column.key === 'project'">
                <RowLogoAndName :projectName="this.entry.project" />
            </div>
            <span class="row-text" v-if="column.key === 'consecutive_days' || column.key === 'authors'">{{
                entry[column.key]
            }}</span>
            <div v-if="column.key === 'price_change'" class="price">
                <RowPrice :priceNumber="priceNumber" :priceString="priceString" />
            </div>
            <div v-if="column.key === 'lines_of_code'" class="bar" :style="{ width: barWidth + '%' }">
                <RowBar :barWidth="barWidth" :barValue="barValue" />
            </div>
        </td>
    </tr>
</template>

<script>

export default {
    components: {
        RowPrice,
        RowBar
    },
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
        priceNumber() {
            return parseInt(this.entry.price_change.match(/-?[\d,]+/)[0].replace(/,/g, ''));
        },
        priceString() {
            return "$" + (this.entry.price_change[0] === '-' ? this.entry.price_change.substr(1) : this.entry.price_change);
        },
    },
};
</script>

<style>
.row-text {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 32px;
    color: #F6F8FF;
}

.bar {
    z-index: 1;
    background-color: #2CC3F3;
    border-radius: 34px;
    height: 25px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.bar-background {
    z-index: -1;
    background-color: #120B26;
    border-radius: 34px;
    height: 25px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    overflow-x: hidden;

}
</style>