<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-4.webp" right>
    <template v-slot:title>
      <SectionTitle class="title-item effect__title">
        <span data-aos="fade-up" data-aos-duration="1000">Эффективный.</span>
        <span data-aos="fade-up" data-aos-duration="1500">работа на обогрев</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text_right">
        Сохраните тепло своего дома с мобильным кондиционером Ballu серии Platinum. Этот прибор
        надежно и эффективно согреет помещение в период холодного межсезонья и в зимние месяцы там,
        где нет центрального отопления или его эффективности не достаточно. Три уровня мощности
        обогрева и управление кондиционером с пульта ДУ подарят легкость и удовольствие от
        использования прибора, а также непревзойденный комфорт вашему дому.
      </p>
    </template>
  </Section>
</template>

<style>
.effect__title {
  width: 100%;
}

@media screen and (max-width: 750px) {
  .effect__title {
    width: 100%;
  }
}

@media screen and (max-width: 500px) {
  .effect__title {
    margin-left: 30px;
  }
}

@media screen and (max-width: 380px) {
  .effect__title {
    margin-left: 30px;
  }
}</style>