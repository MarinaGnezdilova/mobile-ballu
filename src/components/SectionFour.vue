<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-5.webp" id="four">
    <template v-slot:title>
      <SectionTitle class="title-item ">
        <span data-aos="fade-up" data-aos-duration="1000">PLATINUM. 4 В 1 —</span>
        <span data-aos="fade-up" data-aos-duration="1500" class="platinum__title">КОНДИЦИОНЕР, ОСУШИТЕЛЬ,</span>
        <span data-aos="fade-up" data-aos-duration="2500" class="platinum__title">ОБОГРЕВАТЕЛЬ, ВЕНТИЛЯТОР</span>
        <span></span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text">
        Приобретая мобильный кондиционер Ballu серии Platinum вы получаете уникальное устройство,
        сочетающее в себе несколько бытовых климатических приборов. Это мобильный кондиционер для
        жаркого лета там, где невозможно установить классическую сплит-систему. Эффективный
        осушитель воздуха сырой осенью и надежный обогреватель в холодные месяцы.
        Мультифункциональный мобильный кондиционер Ballu серии Platinum круглый год будет вашим
        незаменимым помощником, сохранит бюджет, пространство и истинно комфортную атмосферу вашего
        дома для приятных мгновений с близкими.
      </p>
    </template>
  </Section>
</template>

<style>
.platinum__title {
  width: 30%;
}

@media screen and (max-width: 1280px) {
  .platinum__title {
    width: 100%;
  }
}
</style>