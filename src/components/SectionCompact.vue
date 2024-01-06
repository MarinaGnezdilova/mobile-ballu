<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-7.webp" right id="compact">
    <template v-slot:title>
      <SectionTitle class="title-item compact__title">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Компактный размер</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">в современном дизайне</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text_right">
        Благодаря своим небольшим размерам, мобильные кондиционеры Ballu серии SMART легко и удобно
        использовать для охлаждения небольших помещений, куда крайне неудобно или невозможно
        устанавливать классическую сплит-систему или громоздкие классические мобильные кондиционеры.
        Кондиционеры серии SMART оснащены прочными и подвижными шасси, которые делают приборы очень
        удобными для перемещения по любым напольным покрытиям и установки в необходимое место.
      </p>
    </template>
  </Section>
</template>

<style>
@media screen and (max-width: 950px) {
  .compact__title {
    width: 100%;
  }
}

@media screen and (max-width: 750px) {
  .compact__title {
    width: 100%;
  }
}
</style>