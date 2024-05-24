<template>
    <button class="more-button">Загрузить еще</button>
</template>

<script setup></script>

<style scoped>
.more-button {
    all: unset;
    display: flex;
    padding: 16px 32px;
    justify-content: center;
    align-items: center;
    gap: 8px;
    border-radius: 8px;
    border: 1px solid #002dbf;
    color: #002dbf;
    font-size: 20px;
    font-style: normal;
    font-weight: 600;
    line-height: 120%;
    letter-spacing: -0.2px;
}

.more-button:hover {
    cursor: pointer;
    opacity: 0.8;
}
</style>
