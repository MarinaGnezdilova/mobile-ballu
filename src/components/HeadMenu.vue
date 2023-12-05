<script setup lang="ts">
import { ref, watch } from 'vue';
import type { Ref } from 'vue';
import MenuItem from './MenuItem.vue';

const props = defineProps({
        avtoIsVisible: Boolean,
        silentIsVisible: Boolean,
        energoefIsVisible: Boolean,
        optionsIsVisible: Boolean,
        threeDIsVisible: Boolean,
        compactIsVisible: Boolean,
        dryIsVisible: Boolean,
        nightIsVisible: Boolean
    })

const selectedBlockMain: Ref<'platinum' | 'smart'> = ref('smart');
const selectedBlock: Ref<'3D'|'compact'|'dry'|'night'|'maximum'|'silent'|'energo'|'four'|''> = ref('');
function setValueMain(value: 'platinum' | 'smart') {
    selectedBlockMain.value = value;

}
const setValue = (value:'3D'|'compact'|'dry'|'night'|'maximum'|'silent'|'energo'|'four') => {
    selectedBlock.value = value;
}
watch(props, (newValue) => {
    if(newValue.threeDIsVisible) {
        selectedBlock.value = '3D';
        selectedBlockMain.value = 'smart';
    } else if(newValue.compactIsVisible) {
        selectedBlock.value = 'compact';
        selectedBlockMain.value = 'smart';
    } else if(newValue.dryIsVisible) {
        selectedBlock.value = 'dry';
        selectedBlockMain.value = 'smart';
    } else if (newValue.nightIsVisible) {
        selectedBlock.value = 'night';
        selectedBlockMain.value = 'smart';
    } else if(newValue.avtoIsVisible){
        selectedBlock.value = 'maximum';
        selectedBlockMain.value = 'platinum';
    } else if(newValue.silentIsVisible) {
        selectedBlock.value = 'silent';
        selectedBlockMain.value = 'platinum';
    } else if(newValue.energoefIsVisible) {
        selectedBlock.value = 'energo';
        selectedBlockMain.value = 'platinum';
    } else if(newValue.optionsIsVisible) {
        selectedBlock.value= 'four';
        selectedBlockMain.value = 'platinum';
    } 
    else { 
        selectedBlock.value = '' ;
    }
})
</script>

<template>
  <ul class="header__models">
    <MenuItem 
        text="Platuim" 
        @click="setValueMain('platinum')"
        class="header__item_main"
        :isActive="selectedBlockMain === 'platinum'"
        href="platinum"
    >
    </MenuItem>
    <MenuItem 
        text="Smart" 
        @click="setValueMain('smart')"
        class="header__item_main"
        :isActive="selectedBlockMain === 'smart'"
        href="smart"  
    >
    </MenuItem>
  </ul>
    <ul v-if="selectedBlockMain === 'smart'" class="header__block_active ">
        <MenuItem 
            text="3D" 
            class="header__item" 
            href="3D" 
            @click="setValue('3D')"
            :isActive="selectedBlock === '3D'"
        ></MenuItem>
        <MenuItem 
            text="Компактный размер" 
            class="header__item" 
            href="compact" 
            @click="setValue('compact')"
            :isActive="selectedBlock === 'compact'"
            :delay="300"
        ></MenuItem>
        <MenuItem 
            text="Осушение" 
            class="header__item" 
            href="dry"
            @click="setValue('dry')"
            :isActive="selectedBlock === 'dry'"
            :delay="600"
        ></MenuItem>
        <MenuItem 
            text="Ночной режим" 
            class="header__item" 
            href="night" 
            @click="setValue('night')"
            :isActive="selectedBlock === 'night'"
            :delay="900"
        ></MenuItem>
     </ul>
  <ul v-if="selectedBlockMain === 'platinum'" class="header__block_active">
    <MenuItem 
        text="Авто жалюзи" 
        class="header__item" 
        href="maximum" 
        @click="setValue('maximum')"
        :isActive="selectedBlock === 'maximum'"
    ></MenuItem>
    <MenuItem 
        text="42 дб(а)" 
        class="header__item" 
        href="silent" 
        @click="setValue('silent')"
        :isActive="selectedBlock === 'silent'"
        :delay="300"
    ></MenuItem>
    <MenuItem 
        text="Энергоэффективность «А»" 
        class="header__item" 
        href="energo" 
        @click="setValue('energo')"
        :isActive="selectedBlock === 'energo'"
        :delay="600"
    ></MenuItem>
    <MenuItem 
        text="4 в 1" 
        class="header__item" 
        href="four" 
        @click="setValue('four')"
        :isActive="selectedBlock === 'four'"
        :delay="900"
    ></MenuItem>
  </ul>
</template>

<style scoped></style>
