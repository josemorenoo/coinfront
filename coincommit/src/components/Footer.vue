<template>
    <div class="footer-container">
        <div class="khiza-logo-container">
            <img class="khiza-logo" src="@/assets/khiza.png" />
        </div>
        <p class="copyright">© 2023 Khiza DAO Venture Building</p>
    </div>
</template>

<style>
.footer-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    background-color: #0D071E;
    padding-top: 20px;
    padding-bottom: 20px;
}

.khiza-logo-container {
    margin-left: 10rem;
}


.khiza-logo {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}

.copyright {
    margin-bottom: auto;
    margin-top: auto;
    margin-right: 10rem;

    font-family: 'Public Sans';
    font-style: normal;
    font-weight: 300;
    font-size: 13px;
    line-height: 24px;
    color: #7882AC;
}
</style>
