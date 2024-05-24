<script setup>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Banner from './components/Banner.vue';
import Cards from './components/Cards.vue';
</script>

<template>
    <Header />
    <main class="main">
        <Banner /> 
        <Cards />
    </main>
    <Footer />
</template>

<style scoped>
.main {
    width: 100%;
    display: flex;
    flex-direction: column;
}
</style>
