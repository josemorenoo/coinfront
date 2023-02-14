<template>
    <table class="topten-table">
        <thead class="thead">
            <tr>
                <th class="headers" v-for="column in columns" @click="sortBy(column.key)"
                    :style="{ 'width': this.columnWidths[column.key] + '%' }">
                    {{ column.label }}
                    <span class=" arrow"
                        :class="{ 'arrow-down': sortOrders[column.key] === 1, 'arrow-up': sortOrders[column.key] === -1 }">
                    </span>
                </th>
            </tr>
        </thead>
        <tbody class="tbody">
            <TableRow v-for="entry in filteredData" :entry="entry" :columns="columns" :key="entry.id"
                :maxBarValue="maxBarValue" />
        </tbody>
    </table>
</template>

<script>
import TableRow from './TableRow.vue';

export default {
    components: {
        TableRow,
    },
    data() {
        return {
            sortKey: 'lines_of_code',
            sortOrders: {
                'price_change': 0,
                'consecutive_days': 0,
                'authors': 0,
                'lines_of_code': -1,
            },
            maxBarValue: 0,
            columnWidths: {
                'project': 18,
                'price_change': 18,
                'consecutive_days': 18,
                'authors': 14,
                'lines_of_code': 50,
            }
        };
    },
    props: {
        tableData: Array,
        columns: Array,
    },
    computed: {
        filteredData() {
            let sortKey = this.sortKey;
            let order = this.sortOrders[sortKey] || 1;
            let tableData = this.tableData;
            if (sortKey) {
                tableData = tableData.slice().sort((a, b) => {
                    a = a[sortKey];
                    b = b[sortKey];
                    return (a === b ? 0 : a > b ? 1 : -1) * order;
                });
            }
            return tableData;
        },
        computedMaxBarValue() {
            return Math.max.apply(Math, this.filteredData.map(function (o) { return o.lines_of_code; }));
        }
    },
    mounted() {
        this.maxBarValue = this.computedMaxBarValue;
    },
    methods: {
        sortBy(key) {
            if (key !== 'project') {
                this.sortKey = key;
                let newKeyValue = 1;
                if (this.sortOrders[key] != 0) {
                    newKeyValue = this.sortOrders[key] * -1;
                }

                // reset all the sort keys to remove the arrows first
                Object.keys(this.sortOrders).forEach(key => {
                    this.sortOrders[key] = 0;
                });
                this.sortOrders[key] = newKeyValue;
            }
        },
    },
};
</script>

<style>
.topten-table {
    padding-top: 2rem;
    height: 45rem;
    width: 84%;
}

.thead {
    height: 40px;
}


.headers {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 600;
    font-size: 18px;
    line-height: 24px;
    color: #F6F8FF;
    text-align: left;
    position: relative;
}

.arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    right: 0;
    margin-right: 12px;
}

.arrow-down {
    display: inline-block;
    width: 0;
    height: 0;
    border-left: 4px solid transparent;
    border-right: 4px solid transparent;
    border-top: 4px solid white;
    transform: rotate(0deg);
    margin-left: 5px;
}

.arrow-up {
    display: inline-block;
    width: 0;
    height: 0;
    border-left: 4px solid transparent;
    border-right: 4px solid transparent;
    border-bottom: 4px solid white;
    transform: rotate(-0deg);
    margin-left: 5px;
}
</style>