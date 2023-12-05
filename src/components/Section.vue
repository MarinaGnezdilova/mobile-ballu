<script setup lang="ts">
interface Section {
    src?: string,
    right?: boolean
}
const props = withDefaults(defineProps<Section>(), {
    right: false,
})
</script>
    
<template>
    <section class="section">
        <img class="section-image" :src="src" alt="Фоновое изображение блока" />
        <div class="section__content" :class="{ 'section__content_right': right }">
            <slot name="title"></slot>

            <div class="pros__text-block" :class="{ 'pros__text-block_right': right }">
                <slot name="text"></slot>
            </div>
        </div>
    </section>
</template>