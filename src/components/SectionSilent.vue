<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-2.webp" right id="silent">
    <template v-slot:title>
      <SectionTitle class="title-item title-item_rigth">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300" data-aos-id="super-duper">Очень
          тихий</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">мобильный</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">кондиционер</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text_right" data-aos="zoom-in" data-aos-once="true">
        Наслаждайтесь прохладным воздухом даже жаркими летними ночами с мобильным кондиционером
        Ballu серии Platinum. Мы поднялись на новый уровень и смогли создать почти невозможное —
        безупречно тихий кондиционер. Громкость работы прибора рекордно низкая в своем классе, всего
        42 дБ(А). Мобильный кондиционер Ballu серии Platinum можно использовать круглосуточно, он
        сохранит воздух свежим и не потревожит ваш сон.
      </p>
    </template>
  </Section>
</template>

<style>
.title-item_rigth {
  width: 100%;
}

.pros__first-text {
  width: 50%;
  margin-bottom: 15px;
}

.pros__first-text_right {
  width: 100%;
}
</style>