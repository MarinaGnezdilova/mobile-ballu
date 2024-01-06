<script setup lang="ts">
interface Logo {
    type: 'black' | 'white',
}
const props = withDefaults(defineProps<Logo>(), {
})
</script>

<template>
    <picture class="logo">
        <img v-if="props.type === 'black'" alt="Логотип" class="logo_black" src="/logo-dark.png" loading="lazy" />
        <img v-if="props.type === 'white'" alt="Логотип" class="logo_white" src="/logo-intro.png" loading="lazy" />
    </picture>
</template>

<style>
.logo {
    width: 100%;
    display: flex;
    overflow: hidden;
}

.logo_white {
    width: 38%;
    max-width: 284px;
    min-width: 90px;
}

.logo_black {
    width: 114px;
    height: 39px;
    margin-right: 5%;
    padding-top: 3px;
    float: left;
}

@media screen and (max-width: 1280px) {
    .logo_black {
        width: 90px;
        height: 35px;
    }
}

@media screen and (max-width: 950px) {
    .logo_black {
        margin-right: 2%;
    }
}

@media screen and (max-width: 750px) {
    .logo_black {
        width: 65px;
        height: 23px;
    }
}

@media screen and (max-width: 500px) {
    .logo_black {
        width: 50px;
        height: 20px;
    }
}</style>