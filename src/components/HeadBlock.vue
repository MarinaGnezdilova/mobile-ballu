<script setup lang="ts">
import HeadMenu from './HeadMenu.vue';
import LogoDark from './icons/LogoDark.vue';
const props = defineProps({
    href: String,
    avtoIsVisible: Boolean,
    silentIsVisible: Boolean,
    energoefIsVisible: Boolean,
    optionsIsVisible: Boolean,
    threeDIsVisible: Boolean,
    compactIsVisible: Boolean,
    dryIsVisible: Boolean,
    nightIsVisible: Boolean,
})
const emit = defineEmits(['clickButton']);
</script>
<template>
    <header class="header">
        <nav class="header__container">
            <LogoDark class="header__logo" />
            <HeadMenu :avtoIsVisible="avtoIsVisible" :silentIsVisible="silentIsVisible"
                :energoefIsVisible="energoefIsVisible" :optionsIsVisible="optionsIsVisible"
                :threeDIsVisible="threeDIsVisible" :compactIsVisible="compactIsVisible" :dryIsVisible="dryIsVisible"
                :nightIsVisible="nightIsVisible"></HeadMenu>
        </nav>
        <a href="#countries" class="header__button" @click="$emit('clickButton')">Купить</a>
    </header>
</template>
<style scoped></style>
