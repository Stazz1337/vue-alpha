<template>
    <header class="header">
        <img src="../assets/logo.svg" alt="logo" class="header__logo" />
        <p class="header__text">alpha</p>
    </header>
</template>

<script setup></script>

<style scoped lang="scss">
.header {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    height: 123px;
    width: 100%;
    padding-left: 100px;

    &__logo {
        margin-right: 9px;
    }

    &__text {
        color: #1d37af;
        font-size: 40px;
        font-style: normal;
        font-weight: 900;
        line-height: 120%;
        letter-spacing: -2px;
    }
}
</style>
