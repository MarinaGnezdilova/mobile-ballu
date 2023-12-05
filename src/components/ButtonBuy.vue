<script setup lang="ts">
    interface Button {
        text?: string,
        url?: string,
        tag: string,
        isForOfficalSite?: boolean
        href?: string
    }
    const props = withDefaults(defineProps<Button>(), {
        isForOfficalSite: false,
        tag: "button",
        href: "#countries"
    })

</script>
<template>
    <component :is="tag" class="button" :class="{'button_official-site': isForOfficalSite}" :href="href"> 
        <slot />
        {{ text }}
    </component>

</template>