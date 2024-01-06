<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-3.webp" id="energo">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1000">А класс</span>
        <span data-aos="fade-up" data-aos-duration="1500">эффективности</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text text__class-a">
        Мобильный кондиционер Ballu серии Platinum обладет высоким А-классом энергоэффективности.
        Это означает, что прибор отличается очень экономичным расходом электроэнергии и будет
        идеальным решением для охлаждения, даже при небольших возможностях электросети.
      </p>
    </template>
  </Section>
</template>

<style>
@media screen and (max-width: 750px) {
  .text__class-a {
    width: 52%;
  }
}
</style>
