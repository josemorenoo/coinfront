<template>
    <div class="search-container">
        <input class="search-input" type="text" placeholder="Search Projects" />
        <button class="search-button">
            <i class="fas fa-search"></i>
        </button>
    </div>
</template>



<style scoped>
.search-container {
    height: 30px;
    display: flex;
    align-items: center;
    min-width: 60%;

    padding: 0.5rem;
    mix-blend-mode: normal;

    border: 1px solid #ABB3D7;
    border-radius: 8px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}

.search-input {
    background-color: transparent;
    border: none;
    width: 100%;
    padding: 0.5rem;
    outline: none;

    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 32px;
    color: #ABB3D7;
}

.search-button {
    background-image: url(/src/assets/search.png);
    background-size: cover;
    background-position: center;
    padding: 0.2rem;
    cursor: pointer;
    width: 23px;
    height: 23px;
    margin-right: 6px;
}
</style>