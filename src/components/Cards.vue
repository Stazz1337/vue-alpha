<script setup>
import { ref } from 'vue';
import axios from 'axios';
import MoreButton from './MoreButton.vue';
import Card from './Card.vue';

const newsItems = ref([]);
const currentPage = ref(1);
const nav = ref({});

async function fetchNews() {
    try {
        const response = await axios.get(
            `https://flems.github.io/test/api/news/${currentPage.value}`,
        );
        newsItems.value = [...newsItems.value, ...response.data.items];
        nav.value = response.data.nav;
        currentPage.value += 1;
    } catch (error) {
        console.error(error);
    }
}

function loadMoreNews() {
    if (currentPage.value <= nav.value.total) {
        fetchNews();
    }
}

fetchNews();
</script>

<template>
    <section class="cards">
        <div class="cards__list">
            <Card v-for="(item, index) in newsItems" :key="index" :news="item" />
        </div>
        <div
            class="cards__button-wrapper"
            :class="{ 'nobutton': currentPage > nav.total }">
            <MoreButton @click="loadMoreNews" v-if="currentPage <= nav.total" />
        </div>
    </section>
</template>

<style scoped lang="scss">
.cards {
    padding: 64px 0 0;
    display: flex;
    flex-direction: column;

    &__list {
        width: 100%;
        justify-content: center;
        display: grid;
        grid-template-columns: repeat(auto-fit, 536px);
        gap: 48px 64px;
    }

    &__button-wrapper {
        height: 200px;
        display: flex;
        justify-content: center;
        align-items: center;

        &.nobutton {
            height: 64px;
        }
    }
}
</style>
