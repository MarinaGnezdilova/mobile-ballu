<script setup lang="ts">
interface OtheItem {
    src?: string,
    tag?: string,
    title?: string,
    href?: string
}
const props = withDefaults(defineProps<OtheItem>(), {
    tag: 'div'
})
</script>
<template>
    <component :is="tag" class="other__item">
        <div class="other__item-image-block">
            <img :src="src" class="other__item-image" alt="Другая продукция" />
        </div>
        <slot />
        <h2 class="other__item-title"> {{ title }}</h2>
    </component>
</template>