<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-8.webp" id="dry">
    <template v-slot:title>
      <SectionTitle class="title-item mob-cond__title">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Ballu Smart.</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">Больше чем просто</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">кондиционер</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text">
        Мобильный кондиционер Ballu серии SMART - это не только эффективное мобильное охлаждение, но
        и продуктивное осушение воздуха для небольших помещений с повышенной влажностью (до 30
        л/сутки). Несколько режимов вентиляции без дополнительного охлаждения воздуха расширяют
        сферу применения мобильного кондиционера как в городских условиях, так и на даче или в
        хозяйственных целях.
      </p>
    </template>
  </Section>
</template>

<style>   @media screen and (max-width: 750px) {
     .mob-cond__title {
       width: 100%;
     }

   }
</style>