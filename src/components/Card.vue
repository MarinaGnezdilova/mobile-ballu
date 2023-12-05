<script setup lang="ts">
const props = defineProps({
  card: Object,
  active: Boolean,
  price: String
})
</script>
<template>
  <div class="card__block">
    <div class="card" :class="{ 'card_active': active }">
      <div class="card_image-block">
        <img class="card__image" :src="card?.src" alt="Карточка товара" />
      </div>
      <div class="card__content">
        <h2 class="card__series" :class="{ 'card__content_active': active }">{{ card?.series }}</h2>
        <h3 class="card__model" :class="{ 'card__content_active': active }">{{ card?.model }}</h3>
        <div v-for="(prop, index) in card?.properties" :key="index">
          <h4 class="card__prop" :class="{ 'card__content_active': active }">{{ prop.name }}</h4>
          <p class="card__prop-value" :class="{ 'card__content_active': active }">{{ prop.value }}</p>
        </div>
      </div>
      <p :class="active ? 'card__price_active' : 'card__price'">{{ card?.price }}</p>
    </div>
    <slot />
  </div>
</template>
