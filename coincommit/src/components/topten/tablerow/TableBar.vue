<template>
    <template v-if="this.barWidth >= 10">
        <span class="bar-value">{{ barValueWithCommas }}</span>
    </template>
    <template v-else>
        <span class="bar-value-outside">{{ barValueWithCommas }}</span>
    </template>
</template>

<script>
export default {
    props: {
        barWidth: Number,
        barValue: Number
    },
    computed: {
        barValueWithCommas() {
            return this.barValue.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");;
        },
    }
};
</script>



<style>
.bar-value {
    position: absolute;
    left: 5px;
    padding: 0.25rem;
    font-size: 12px;
    color: #120B26
}

.bar-value-outside {
    position: absolute;
    left: 5px;
    bottom: 0;
    padding: 0.25rem;
    font-size: 12px;
    color: #F6F8FF;
    min-width: 1rem;
    white-space: nowrap;
    left: 100%;
}
</style>