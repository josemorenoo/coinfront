<template>
    <div class="time-frame-selector">
        <div class="time-frame" v-for="timeFrame in timeFrames" :key="timeFrame.value"
            @click="selectTimeFrame(timeFrame)" :class="{ 'selected-tf': timeFrame.value === selectedTimeFrame }">
            <div class="label-text">
                {{ timeFrame.label }}
            </div>

        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedTimeFrame: '1D',
            timeFrames: [
                { label: '1D', value: '1D' },
                { label: '7D', value: '7D' },
                { label: '1M', value: '1M' },
                { label: '3M', value: '3M' },
                { label: '1Y', value: '1Y' },
                { label: 'YTD', value: 'YTD' },
                { label: 'ALL', value: 'ALL' }
            ]
        };
    },
    methods: {
        selectTimeFrame(timeFrame) {
            this.selectedTimeFrame = timeFrame.value;
            this.$emit('select', timeFrame);
        }
    }
};
</script>

<style>
.time-frame-selector {
    padding-left: 5px;
    padding-right: 5px;
    display: flex;
    gap: 10px;
    width: fit-content;
    border: 1px solid #ABB3D7;
    border-radius: 8px;
}

.time-frame {
    height: 36px;
    width: 36px;
    margin-top: auto;
    margin-bottom: auto;
    cursor: pointer;
}

.selected-tf {
    background-color: #F6F8FF;
    height: 36px;
    width: 36px;
    border-radius: 8px;
    margin-top: auto;
    margin-bottom: auto;
    cursor: pointer;
}


.label-text {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 100%;
    color: #20254A;

    justify-content: center;
    display: flex;

    position: relative;
    top: 50%;
    transform: translateY(-50%);
}
</style>