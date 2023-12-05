<script setup lang="ts">
interface Badge {
    title?: string
    description?: string
    union?: string
    tag: string
}
const props = withDefaults(defineProps<Badge>(), {
   tag: 'div'
})
</script>
<template>
    <component class="badge" :is="tag">
        <slot />
        <div class="badge__title-block">
            <p class="badge__title">  {{ title }}</p>
            <p class="badge__description">  {{ union }}</p>
        </div>
        <span class="badge__description">{{ description }}</span>
    </component>
</template>
<style scoped>
</style>