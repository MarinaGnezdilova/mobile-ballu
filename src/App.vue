<script setup lang="ts">
import { ref, onMounted } from 'vue';
import type { VNodeRef } from 'vue';
import HeadBlock from './components/HeadBlock.vue';
import SectionTitle from './components/SectionTitle.vue';
import Card from './components/Card.vue';
import ButtonBuy from './components/ButtonBuy.vue';
import AddressTable from './components/AddressTable.vue';
import ParthnersPopup from './components/ParthnersPopup.vue';
import FooterVue from './components/FooterVue.vue';
import PlatinumIntro from './components/PlatinumIntro.vue';
import SmartIntro from './components/SmartIntro.vue';
import OtherSection from './components/OtherSection.vue';
import SectionMaximum from './components/SectionMaximum.vue';
import SectionSilent from './components/SectionSilent.vue';
import SectionEnergo from './components/SectionEnergo.vue';
import SectionEffective from './components/SectionEffective.vue';
import SectionFour from './components/SectionFour.vue';
import SectionThreeD from './components/SectionThreeD.vue';
import SectionCompact from './components/SectionCompact.vue';
import SectionDry from './components/SectionDry.vue';
import SectionNight from './components/SectionNight.vue';
import { platinumSeries, smartElectronic, smartMechanic, smartPro } from '@/mock/models';
import { useIntersectionObserver } from '@vueuse/core';
import AOS from 'aos';
import 'aos/dist/aos.css';

onMounted(() => {
  AOS.init({
    disable: 'mobile',
  })
});
window.addEventListener('load', AOS.refresh);

const leftDevicePlatinum = platinumSeries.slice(0, 2);
const rightDevicePlatinum = platinumSeries.slice(2);


const isParthnersFirstBlockHidden = ref<boolean>(true);
const isParthnersSecondBlockHidden = ref<boolean>(true);
const isParthnersThirdBlockHidden = ref<boolean>(true);
const isParthnersForthBlockHidden = ref<boolean>(true);
const isPopupOpen = ref<boolean>(false);
const currentCity = ref<string>('');
interface Sections {
  avtoIsVisible: string,
  silentIsVisible: string,
  energoefIsVisible: string,
  optionsIsVisible: string,
  threeDIsVisible: string,
  compactIsVisible: string,
  dryIsVisible: string,
  nightIsVisible: string,
  mainBlockName: string
};

const sections = ref<Sections>({
  avtoIsVisible: '',
  silentIsVisible: '',
  energoefIsVisible: '',
  optionsIsVisible: '',
  threeDIsVisible: '',
  compactIsVisible: '',
  dryIsVisible: '',
  nightIsVisible: '',
  mainBlockName: ''
}
)
const avto = ref<VNodeRef>('');
const silent = ref<VNodeRef>('');
const energoef = ref<VNodeRef>('');
const options = ref<VNodeRef>('');
const threeD = ref<VNodeRef>('');
const compact = ref<VNodeRef>('');
const dry = ref<VNodeRef>('');
const night = ref<VNodeRef>('');

useIntersectionObserver(
  avto,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.avtoIsVisible = 'maximum';
      sections.value.mainBlockName = 'platinum';
    } else {
      sections.value.avtoIsVisible = '';
    }
  },
);
useIntersectionObserver(
  silent,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.silentIsVisible = 'silent';
      sections.value.mainBlockName = 'platinum';
      sections.value.avtoIsVisible = '';
    } else {
      sections.value.silentIsVisible = '';
    }
  },
);
useIntersectionObserver(
  energoef,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.energoefIsVisible = 'energo';
      sections.value.silentIsVisible = '';
      sections.value.mainBlockName = 'platinum';
    } else {
      sections.value.energoefIsVisible = '';
    }
  },
);
useIntersectionObserver(
  options,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.optionsIsVisible = 'four';
      sections.value.mainBlockName = 'platinum';
    } else {
      sections.value.optionsIsVisible = '';
    }
  },
);
useIntersectionObserver(
  threeD,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.threeDIsVisible = '3D';
      sections.value.mainBlockName = 'smart';
    } else {
      sections.value.threeDIsVisible = '';
    }
  },
);
useIntersectionObserver(
  compact,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.compactIsVisible = 'compact';
      sections.value.threeDIsVisible = '';
      sections.value.mainBlockName = 'smart';
    } else {
      sections.value.compactIsVisible = '';
    }
  },
);
useIntersectionObserver(
  dry,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.dryIsVisible = 'dry';
      sections.value.compactIsVisible = '';
      sections.value.mainBlockName = 'smart';
    } else {
      sections.value.dryIsVisible = '';
    }
  },
);
useIntersectionObserver(
  night,
  ([{ isIntersecting }]) => {
    if (isIntersecting) {
      sections.value.nightIsVisible = 'night';
      sections.value.dryIsVisible = '';
      sections.value.mainBlockName = 'smart';
    } else {
      sections.value.nightIsVisible = '';
    }
  },
);

const handleClickFirstBlock = (): void => {
  isParthnersFirstBlockHidden.value = !isParthnersFirstBlockHidden.value;
  if (isParthnersSecondBlockHidden.value === false || isParthnersThirdBlockHidden.value === false || isParthnersForthBlockHidden.value === false) {
    isParthnersSecondBlockHidden.value = true;
    isParthnersThirdBlockHidden.value = true;
    isParthnersForthBlockHidden.value = true;
  }
};
const handleClickSecondBlock = (): void => {
  isParthnersSecondBlockHidden.value = !isParthnersSecondBlockHidden.value;
  if (isParthnersFirstBlockHidden.value === false || isParthnersThirdBlockHidden.value === false || isParthnersForthBlockHidden.value === false) {
    isParthnersFirstBlockHidden.value = true;
    isParthnersThirdBlockHidden.value = true;
    isParthnersForthBlockHidden.value = true;
  }
};
const handleClickThirdBlock = (): void => {
  isParthnersThirdBlockHidden.value = !isParthnersThirdBlockHidden.value;
  if (isParthnersFirstBlockHidden.value === false || isParthnersSecondBlockHidden.value === false || isParthnersForthBlockHidden.value === false) {
    isParthnersFirstBlockHidden.value = true;
    isParthnersSecondBlockHidden.value = true;
    isParthnersForthBlockHidden.value = true;
  }
};
const handleClickForthBlock = (): void => {
  isParthnersForthBlockHidden.value = !isParthnersForthBlockHidden.value;
  if (isParthnersFirstBlockHidden.value === false || isParthnersSecondBlockHidden.value === false || isParthnersThirdBlockHidden.value === false) {
    isParthnersFirstBlockHidden.value = true;
    isParthnersSecondBlockHidden.value = true;
    isParthnersThirdBlockHidden.value = true;
  }
};
const selectCity = (city: string): void => {
  isPopupOpen.value = true;
  currentCity.value = city;
};
const closePopup = (): void => {
  isPopupOpen.value = false;
};
</script>

<template>
  <HeadBlock @clickButton="handleClickFirstBlock" :isVisibleForMenu="sections" />

  <PlatinumIntro />

  <SectionMaximum ref="avto" />

  <SectionSilent ref="silent" />

  <SectionEnergo ref="energoef" />

  <SectionEffective />

  <SectionFour ref="options" />

  <section v-if="platinumSeries.length > 0" class="compare">
    <SectionTitle class="title-item compare__title">
      <span>ТАБЛИЦА СРАВНЕНИЯ МОДЕЛЕЙ</span>
    </SectionTitle>
    <div class="compare__table">
      <div class="compare-column compare-column_left">
        <Card v-for="card in leftDevicePlatinum" :key="card.model" :card="card" :active="card.model === 'BPHS-09H'">
          <ButtonBuy text="Купить на shop.ballu.ru" isForOfficalSite href="#" />
          <ButtonBuy text="Купить у  партнеров" @click="handleClickFirstBlock" href="#countries" />
        </Card>
      </div>
      <div class="compare-column compare-column_right">
        <Card v-for="card in rightDevicePlatinum" :key="card.model" :card="card">
          <ButtonBuy text="Купить на shop.ballu.ru" isForOfficalSite href="#" />
          <ButtonBuy text="Купить у  партнеров" @click="handleClickFirstBlock" href="#countries" />
        </Card>
      </div>
    </div>
  </section>

  <section id="parthners" :class="{ 'hidden': isParthnersFirstBlockHidden }">
    <div id="countries"></div>
    <AddressTable @clickCity="selectCity" />
  </section>

  <SmartIntro />

  <SectionThreeD ref="threeD" />

  <SectionCompact ref="compact" />

  <SectionDry ref="dry" />

  <SectionNight ref="night" />

  <section v-if="smartElectronic.length > 0 || smartMechanic.length > 0 || smartPro.length > 0" class="compare">
    <SectionTitle class="title-item compare__title">
      <span>Таблица СРАВНЕНИЯ МОДЕЛЕЙ</span>
    </SectionTitle>
    <div class="compare__table">
      <div class="compare-column compare__smart-el">
        <Card v-for="card in smartElectronic" :key="card.model" :card="card" :active="card.model === 'BPAC-07 CE_1'"
          class="compare_smart-el-card">
          <ButtonBuy text="Купить на shop.ballu.ru" isForOfficalSite href="#" />
          <ButtonBuy text="Купить у  партнеров" @click="handleClickSecondBlock" href="#countries_smart" />
        </Card>
      </div>
    </div>

    <div class="parthners" :class="{ 'hidden': isParthnersSecondBlockHidden }">
      <div id="countries_smart"></div>
      <AddressTable @clickCity="selectCity" />
    </div>

    <div class="compare__table">
      <div class="compare-column compare-mechanic-block">
        <Card v-for="card in smartMechanic" :key="card.model" :card="card">
          <ButtonBuy text="Купить на shop.ballu.ru" isForOfficalSite href="#" />
          <ButtonBuy text="Купить у  партнеров" @click="handleClickThirdBlock" href="#countries_smart-mechanic" />
        </Card>
      </div>
    </div>

    <div class="parthners" :class="{ 'hidden': isParthnersThirdBlockHidden }">
      <div id="countries_smart-mechanic"></div>
      <AddressTable @clickCity="selectCity" />
    </div>

    <div class="compare__table ">
      <div class="compare-column compare-pro__block">
        <Card v-for="card in smartPro" :key="card.model" :card="card">
          <ButtonBuy text="Купить на shop.ballu.ru" isForOfficalSite href="#" />
          <ButtonBuy text="Купить у  партнеров" @click="handleClickForthBlock" href="#countries_smart-pro" />
        </Card>
      </div>
    </div>

    <div class="parthners" :class="{ 'hidden': isParthnersForthBlockHidden }">
      <div id="countries_smart-pro"></div>
      <AddressTable @clickCity="selectCity" />
    </div>

  </section>

  <OtherSection />

  <FooterVue />

  <ParthnersPopup :class="{ 'popup_hidden': !isPopupOpen }" :selectedCity="currentCity" @close="closePopup" />
</template>

<style>
.title-item {
  width: 65%;
  font-size: 3.8em;
  text-transform: uppercase;
  font-weight: lighter;
  margin-top: 70px;
  line-height: 1;
}

.compare__title {
  margin-top: 30px;
}

.compact__title {
  width: 100%;
}

.compare__title {
  width: 100%;
  text-align: center;
}

.compare {
  display: flex;
  align-items: center;
  flex-direction: column;
  text-align: center;
}

.compare__table {
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 50px;
  margin-bottom: 100px;
}

.compare-column {
  display: flex;
}

.compare-column_left {
  margin-right: 25px;
}

.compare-column_right {
  margin-left: 25px;
}

.compare__card-block {
  width: 60%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.compare-mechanic-block {
  margin-top: 0;
}

.compare__smart-el-block {
  margin-bottom: 50px;
  margin-bottom: 0;
}

.hidden {
  display: none;
}

@media screen and (max-width: 1280px) {
  .title-item {
    font-size: 2.5em;
  }
}

@media screen and (max-width: 950px) {
  .other__row {
    flex-direction: column;
  }

  .title-item {
    font-size: 1.8em;
  }

  .compare__table {
    margin-top: 30px;
    margin-bottom: 70px;
  }

  .compare-column_left {
    margin-right: 15px;
  }

  .compare-column_right {
    margin-left: 15px;
  }

  .compare-pro__block {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
}

@media screen and (max-width: 750px) {
  .title-item {
    font-size: 1.2em;
    width: 65%;
    margin-top: 20px;
  }

  .compare__table {
    flex-direction: column;
    align-items: center;
  }

  .compare-column_left {
    margin-right: 0;
  }

  .compare-column_right {
    margin-left: 0;
  }

  .compare__smart-el {
    flex-direction: column;
    width: 50%;
    margin: 0 auto;
  }

  .parthners {
    margin-left: 8.85%;
  }
}

@media screen and (max-width: 500px) {
  .title-item {
    font-size: 0.8em;
  }

  .section__content {
    left: 2%;
  }

  .card__model {
    font-size: 1.8em;
  }

  .compare__table {
    margin-bottom: 30px;
  }

  .compare-column_left {
    display: grid;
    grid-template-columns: 1fr;
  }

  .compare-column_right {
    display: grid;
    grid-template-columns: 1fr;
  }

  .compare-mechanic-block {
    display: flex;
    flex-direction: column;
  }

  .compare-pro__block {
    grid-template-columns: 1fr;
  }
}

@media screen and (max-width: 380px) {
  .title-item {
    margin-top: 21px;
    font-size: 0.7em;
  }
}</style>
