<script setup lang="ts">
import { parthnersBalakovo } from '@/mock/parthners';
const props = defineProps({
    selectedCity: String
})
const emit = defineEmits(['close']);
</script>
<template>
    <div class="partheners-popup">
        <div class="partheners-popup__container">
            <h2 class="partheners-popup__city">{{ selectedCity }}</h2>
            <div class="partheners-popup__button-close " @click="$emit('close')"></div>
            <ul class="partheners-popup__list">
                <li v-for="(item, index) in parthnersBalakovo" :key="index">
                    <p class="partheners-popup__parthner">{{ item.name }}</p>
                    <p v-if="item.site" class="partheners-popup__site">{{ item.site }}</p>
                    <p v-if="item.address" class="partheners-popup__about-pathner">Адрес:{{ item.address }}</p>
                    <p v-if="item.contacts" class="partheners-popup__about-pathner">Тел.: {{ item.contacts }}</p>
                </li>
            </ul>
        </div>
    </div>
</template>