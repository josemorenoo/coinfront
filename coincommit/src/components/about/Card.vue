<template>
    <div class="card">
        <div class="logo-container">
            <img class="logo" src="@/assets/moon.png" />
        </div>
        <p class="card-text">{{ cardText }}</p>
    </div>
</template>

<script>
export default {
    props: {
        cardText: {
            type: String,
            required: true
        },
    },
};
</script>

<style>
.card {
    display: flex;
    flex-direction: column;
    background-color: #20254A;
    border-radius: 8px;
}

.logo {
    margin-left: 40px;
    margin-top: 40px;
}

.card-text {
    margin-left: 40px;
    margin-right: 40px;
    margin-bottom: 40px;
    margin-top: 20px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 24px;
    line-height: 150%;

    display: flex;
    align-items: center;

    color: #FFFFFF;
}
</style>