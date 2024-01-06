<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-6.webp" id="3D">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Интелектуальный</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">3-D воздушный</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">поток</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text">
        Мобильные кондиционеры Ballu серии SMART позволяют регулировать направление воздушного
        потока в четырех направлениях* — вертикальные и горизонтальные жалюзи прибора свободно
        поворачиваются на 180°, равномерно распределяя прохладный воздух по всему помещению в
        автоматическом режиме. <br> * Автоматические жалюзи в моделях BPAC-07 CE_17Y, BPAC-09 CE_17Y, BPAC-12 CE_17Y
      </p>
    </template>
  </Section>
</template>
