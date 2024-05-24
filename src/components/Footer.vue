<template>
    <header class="footer">
        <div class="footer__wrapper">
            <img src="../assets/logo.svg" alt="logo" class="footer__logo" />
            <p class="footer__text">alpha</p>
        </div>

        <p class="footer__copyright">© alpha, 2024</p>
    </header>
</template>

<script setup></script>

<style scoped lang="scss">
.footer {
    display: flex;
    flex-direction: column;
    height: 202px;
    width: 100%;
    padding-left: 100px;
    background: #f0f6fe;
    gap: 16px;
    justify-content: center;

    &__wrapper {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        width: 100%;
    }

    &__logo {
        margin-right: 9px;
        width: 31.5px;
    }

    &__text {
        color: #1d37af;
        font-size: 30px;
        font-style: normal;
        font-weight: 900;
        line-height: 120%;
        letter-spacing: -1.5px;
    }

    &__copyright {
        margin: 0;
        color: #81899d;
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 140%;
    }
}
</style>
