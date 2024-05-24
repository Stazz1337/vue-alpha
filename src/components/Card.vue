<template>
    <div class="card">
        <img v-if="news.image" class="card__image" :src="news.image" :alt="news.name" />

        <div class="card__content" :class="{ 'has-image': news.image }">
            <div class="card__date">
                <p class="card__date-day">{{ day }}</p>

                <div class="card__date-wrapper">
                    <p class="card__date-month">{{ month }}</p>

                    <p class="card__date-year">{{ year }}</p>
                </div>
            </div>

            <h2 class="card__title">{{ news.name }}</h2>

            <p class="card__text">{{ news.previewText }}</p>

            <p class="card__tag">{{ news.type.value }}</p>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import moment from 'moment';

const props = defineProps({
    news: Object,
});

const dateObject = new Date(props.news.date * 1000);
const formattedDate = moment(dateObject).format('DD MMMM YYYY');

const day = ref(formattedDate.split(' ')[0]);
const month = ref(formattedDate.split(' ')[1]);
const year = ref(formattedDate.split(' ')[2]);
</script>

<style scoped lang="scss">
.card {
    width: 536px;

    border-radius: 16px;
    border: 1px solid #0f62fe;

    &__image {
        width: 100%;
        height: 250px;
        object-fit: cover;
        border-radius: 16px 16px 0 0;
    }

    &__content {
        padding: 32px;
        display: flex;
        flex-direction: column;
        gap: 16px;
        height: 100%;

        &.has-image {
            height: calc(100% - 250px);
        }
    }

    &__date {
        display: flex;
        align-items: center;
        gap: 4px;
        height: 36px;
        color: #a1a7b5;
        font-style: normal;
        letter-spacing: -0.15px;
    }

    &__date-day {
        font-size: 36px;
        font-weight: 400;
    }

    &__date-wrapper {
        display: flex;
        flex-direction: column;
    }

    &__date-month {
        font-size: 15px;
        font-weight: 700;
        line-height: 110%;
    }

    &__date-year {
        font-size: 15px;
        font-weight: 700;
        line-height: 110%;
    }

    &__title {
        color: #0c5bef;
        font-size: 22px;
        font-style: normal;
        font-weight: 400;
        line-height: 120%;
    }

    &__text {
        color: #222327;

        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 130%;
        letter-spacing: -0.2px;
        margin-bottom: 24px;
    }

    &__tag {
        display: flex;
        margin-top: auto;
        width: fit-content;
        padding: 4px 16px;
        height: 28px;
        justify-content: center;
        align-items: center;
        gap: 2px;
        border-radius: 16px;
        background: #f0f6fe;
        color: #00133a;
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 140%;
    }
}
</style>
