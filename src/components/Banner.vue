<template>
    <section class="banner">
        <h1 class="banner__title">Новости</h1>
    </section>
</template>

<script setup></script>

<style scoped lang="scss">
.banner {
    height: 320px;
    width: 100%;
    display: flex;
    align-items: flex-end;
    background-image: url('../assets/banner.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

    &__title {
        color: #17171a;
        font-size: 40px;
        font-style: normal;
        font-weight: 700;
        line-height: 120%;
        letter-spacing: -0.4px;
        margin: 0 0 48px 100px;
    }
}
</style>
