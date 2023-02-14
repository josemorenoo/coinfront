<template>
    <div class="logo-component">
        <img class="logo" :src="`./src/assets/logos/${projectName.toUpperCase()}.png`"
            :onerror="`this.src='./src/assets/logos/default.png'; this.classList.add('logo');`"> <span
            class="project-name">{{
    projectName.toUpperCase()
            }}</span>
    </div>
</template>

<script>
export default {
    props: {
        projectName: {
            type: String,
            required: true
        }
    }
};
</script>

<style>
.logo-component {
    display: flex;
    align-items: center;
}

.logo {
    height: 35px;
    width: 35px;
    margin-right: 20px;
}

.project-name {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 32px;
    color: #F6F8FF;
}
</style>