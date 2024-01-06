<script setup lang="ts">
import LogoBallu from './icons/LogoBallu.vue';
import Badge from './icons/Badge.vue';
import { badges } from '@/mock/badges';
</script>

<template>
    <section class="about" id="smart">
        <picture class="about__picture">
            <img alt="серия smart" class="about__image" src="/bg-intro-2.webp" loading="lazy" />
        </picture>
        <div class="about__block smart__block">
            <div>
                <LogoBallu type="white" />
                <div class="about__title smart__title">
                    <span class="about__text" data-aos="fade-up" data-aos-duration="1000">Расширяя границы</span>
                    <span class="about__text" data-aos="fade-up" data-aos-duration="1500">мобильные</span>
                    <span class="about__text" data-aos="fade-up" data-aos-duration="2000">кондиционеры</span>
                    <span class="about__text" data-aos="fade-up" data-aos-duration="2500">для дома и бизнеса</span>
                </div>
            </div>
            <div>
                <p class="about__subtitle" data-aos="fade-up" data-aos-duration="1000">Мобильный кондиционер</p>
                <div class="about__subtitle-block">
                    <p class="about__big" data-aos="fade-up" data-aos-duration="1500">серия</p>
                    <p class="about__small" data-aos="fade-up" data-aos-duration="1500">Smart</p>
                </div>
                <ul class="about__badges smart__badges">
                    <Badge v-for="(badge, index) in badges.platinum" :key="index" data-aos="zoom-in-up"
                        data-aos-duration="500" :data-aos-delay="(index + 1) * 400" :title="badge.title"
                        :description="badge.description" :union="badge.union" />
                </ul>
            </div>
        </div>
        <img alt="Мобильный кондиционер Smart" class="about__image-device" data-aos="fade-up" data-aos-duration="2000"
            src="/device-intro-2.png" />
    </section>
</template>

<style>
.smart__block {
    top: 7%;
}

@media screen and (max-width: 750px) {
    .smart__text {
        height: 80%;
    }

    .smart__title {
        margin-bottom: calc(var(--index) * 4);
    }
}

@media screen and (max-width: 500px) {
    .smart__block {
        top: 3%;
        height: 100%;
    }

    .smart__title {
        margin-bottom: calc(var(--index) * 0.5);
    }
}
</style>