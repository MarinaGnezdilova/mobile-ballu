<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
  <Section src="/bg-9.webp" right id="night">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Мобильный кондиционер smart.</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">Дополнительные преимущества</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text_right">
        Мы расширили возможности мобильных
        кондиционеров SMART удобными функциями. А-класс энергоэффективности для
        максимальной экономии. Автоматическое испарение конденсата и таймер отложенного старта/выключения для автономной
        работы. Низкий уровень шума 45 дБ(А) и ночной режим для спокойного сна. Интуитивно понятное управление в SMART
        Mechanic и
        пульт ДУ в SMART Electronic.
      </p>
    </template>
  </Section>
</template>