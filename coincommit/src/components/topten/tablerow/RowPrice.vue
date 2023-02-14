<template>
    <div :style="styleObject">
        {{ priceString }}
    </div>
</template>

<script>
export default {
    props: {
        priceNumber: Number,
        priceString: String
    },
    computed: {
        styleObject() {
            let color = this.priceNumber >= 0 ? '#5EEA7C' : '#CE2222'
            return {
                backgroundColor: 'transparent',
                border: `1px solid ${color}`,
                color: color,
                padding: '5px',
                borderRadius: '8px',
                width: 'fit-content',
                paddingLeft: '1rem',
                paddingRight: '1rem'
            }
        }
    }
}
</script>