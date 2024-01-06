<script setup lang="ts">
import MenuItem from './MenuItem.vue';
import { menuPlatinum, menuSmart} from '@/constant/itemsMenu';
import type { VisibilitySections } from '@/components/HeadBlock.vue';

const props = withDefaults(defineProps<VisibilitySections>(), {
});
</script>

<template>
  <ul class="header__models">
    <MenuItem text="Platuim" :isActive="isVisibleForMenu.mainBlockName === 'platinum'" href="platinum"/>
    <MenuItem text="Smart" :isActive="isVisibleForMenu.mainBlockName === 'smart'" href="smart" />
  </ul>
    <ul v-if="isVisibleForMenu.mainBlockName === 'smart'" class="header__block_active ">
        <MenuItem 
            v-for="(item, index) in menuSmart"
            :key=index
            :text="item.text"
            :href="item.href"
            :delay="300*(index+1)"
            :isActive="isVisibleForMenu[item.valueForMatchingWithProps] === item.name"
        />
     </ul>
  <ul v-if="isVisibleForMenu.mainBlockName === 'platinum'" class="header__block_active">
    <MenuItem 
        v-for="(item, index) in menuPlatinum"
        :key="index"
        :text="item.text"
        :href="item.href"
        :delay="300*(index + 1)"
        :isActive="isVisibleForMenu[item.valueForMatchingWithProps] === item.name"
     />
  </ul>
</template>

<style>
.header__models {
  position: relative;
  display: flex;
  background-image: url('/nav-arrow.png');
  background-position: right center;
  background-repeat: no-repeat;
}
.header__models:before {
  content: '';
  height: 30px;
  width: 1px;
  transform: translateY(25%);
  background: var(--color-green);
}
@media screen and (max-width: 1280px) {
    .header__models {
    background-size: 8px 20px;
  }
}
@media screen and (max-width: 950px) {
    .header__models:before {
    height: 25px;
  }
}
@media screen and (max-width: 750px) {
    .header__models {
    background-size: 5px 12px;
  }
  .header__models:before {
    transform: translateY(0%);
    height: 18px;
  }
}
@media screen and (max-width: 500px) {
    .header__models {
    background-size: 4px 8px;
  }
  .header__models:before {
    display: none;
  }    
}
@media screen and (max-width: 380px) {
  .header__models {
    background-image: none;
    border-right: solid 1px var(--color-green);
  }
}
</style>
