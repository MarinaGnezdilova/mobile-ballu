<script setup lang="ts">
interface MenuItem {
    text?: string
    href?: string
    isActive: boolean
    delay?: Number
}
const props = withDefaults(defineProps<MenuItem>(), {
})
</script>

<template>
    <li class="nav__item" :class="{ 'nav__item_active': isActive }">
        <a data-aos="fade-left" data-aos-duration="1500" :data-aos-delay="`${delay}`" class="nav__item-link"
            :href="`#${href}`">
            {{ text }}
            <slot />
        </a>
    </li>
</template>
<style scoped></style>