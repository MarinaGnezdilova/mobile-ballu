<script setup lang="ts">
import { ref, onMounted } from 'vue';
import HeadBlock from './components/HeadBlock.vue';
import LogoWhite from './components/icons/LogoWhite.vue';
import Badge from './components/icons/Badge.vue';
import SectionTitle from './components/SectionTitle.vue';
import Section from './components/Section.vue';
import Card from './components/Card.vue';
import ButtonBuy from './components/ButtonBuy.vue';
import OtherItem from './components/OtherItem.vue';
import AddressTable from './components/AddressTable.vue';
import ParthnersPopup from './components/ParthnersPopup.vue';
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
const isParthnersFirstBlockHidden = ref(true);
const isParthnersSecondBlockHidden = ref(true);
const isParthnersThirdBlockHidden = ref(true);
const isParthnersForthBlockHidden = ref(true);
const isPopupOpen = ref(false);
const currentCity = ref('');

const avto = ref(null);
const avtoIsVisible = ref(false);
const silent = ref(null);
const silentIsVisible = ref(false);
const energoef = ref(null);
const energoefIsVisible = ref(false);
const options = ref(null);
const optionsIsVisible = ref(false);
const threeD = ref(null);
const threeDIsVisible = ref(false);
const compact = ref(null);
const compactIsVisible = ref(false);
const dry = ref(null);
const dryIsVisible = ref(false);
const night = ref(null);
const nightIsVisible = ref(false);
useIntersectionObserver(
  avto,
  ([{ isIntersecting }]) => {
    avtoIsVisible.value = isIntersecting
  },
);
useIntersectionObserver(
  silent,
  ([{ isIntersecting }]) => {
    silentIsVisible.value = isIntersecting;
    avtoIsVisible.value = false
  },
);
useIntersectionObserver(
  energoef,
  ([{ isIntersecting }]) => {
    energoefIsVisible.value = isIntersecting;
    silentIsVisible.value = false;
  },
);
useIntersectionObserver(
  options,
  ([{ isIntersecting }]) => {
    optionsIsVisible.value = isIntersecting
  },
);
useIntersectionObserver(
  threeD,
  ([{ isIntersecting }]) => {
    threeDIsVisible.value = isIntersecting
  },
);
useIntersectionObserver(
  compact,
  ([{ isIntersecting }]) => {
    compactIsVisible.value = isIntersecting;
    threeDIsVisible.value = false;
  },
);
useIntersectionObserver(
  dry,
  ([{ isIntersecting }]) => {
    dryIsVisible.value = isIntersecting;
    compactIsVisible.value = false;
  },
);
useIntersectionObserver(
  night,
  ([{ isIntersecting }]) => {
    nightIsVisible.value = isIntersecting;
    dryIsVisible.value = false;
  },
);

function handleClickFirstBlock() {
  isParthnersFirstBlockHidden.value = !isParthnersFirstBlockHidden.value;
  if (isParthnersSecondBlockHidden.value === false || isParthnersThirdBlockHidden.value === false || isParthnersForthBlockHidden.value === false) {
    isParthnersSecondBlockHidden.value = true;
    isParthnersThirdBlockHidden.value = true;
    isParthnersForthBlockHidden.value = true;
  }
};
function handleClickSecondBlock() {
  isParthnersSecondBlockHidden.value = !isParthnersSecondBlockHidden.value;
  if (isParthnersFirstBlockHidden.value === false || isParthnersThirdBlockHidden.value === false || isParthnersForthBlockHidden.value === false) {
    isParthnersFirstBlockHidden.value = true;
    isParthnersThirdBlockHidden.value = true;
    isParthnersForthBlockHidden.value = true;
  }
};
function handleClickThirdBlock() {
  isParthnersThirdBlockHidden.value = !isParthnersThirdBlockHidden.value;
  if (isParthnersFirstBlockHidden.value === false || isParthnersSecondBlockHidden.value === false || isParthnersForthBlockHidden.value === false) {
    isParthnersFirstBlockHidden.value = true;
    isParthnersSecondBlockHidden.value = true;
    isParthnersForthBlockHidden.value = true;
  }
};
function handleClickForthBlock() {
  isParthnersForthBlockHidden.value = !isParthnersForthBlockHidden.value;
  if (isParthnersFirstBlockHidden.value === false || isParthnersSecondBlockHidden.value === false || isParthnersThirdBlockHidden.value === false) {
    isParthnersFirstBlockHidden.value = true;
    isParthnersSecondBlockHidden.value = true;
    isParthnersThirdBlockHidden.value = true;
  }
};
function selectCity(city: string) {
  isPopupOpen.value = true;
  currentCity.value = city;
};
function closePopup() {
  isPopupOpen.value = false;
};
</script>

<template>
  <HeadBlock @clickButton="handleClickFirstBlock" :avtoIsVisible="avtoIsVisible" :silentIsVisible="silentIsVisible"
    :energoefIsVisible="energoefIsVisible" :optionsIsVisible="optionsIsVisible" :threeDIsVisible="threeDIsVisible"
    :compactIsVisible="compactIsVisible" :dryIsVisible="dryIsVisible" :nightIsVisible="nightIsVisible">
  </HeadBlock>
  <section class="about" id="platinum">
    <img alt="Серия Paltinum" class="about__image about-first__image" src="/bg-intro-1.jpg" />
    <div class="about__text-block">
      <div>
        <LogoWhite />
        <h2 class="about__title">
          <span class="about__title-item" data-aos="fade-up" data-aos-duration="1000">Надежная работа</span>
          <span class="about__title-item" data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">на
            охлаждение</span>
          <span class="about__title-item" data-aos="fade-up" data-aos-duration="2000" data-aos-delay="600">и
            обогрев</span>
        </h2>
      </div>
      <div>
        <span class="about__subtitle" data-aos="fade-up" data-aos-duration="1000">Мобильный кондиционер</span>
        <div class="about__subtitle-block">
          <p class="about__big-subtitle" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200"
            data-aos-delay="300">серия</p>
          <p class="about__small-subtitle" data-aos="fade-up" data-aos-duration="1500" data-aos-offset="-200"
            data-aos-delay="300">Platinum</p>
        </div>
        <ul class="about__badges">
          <Badge data-aos="zoom-in" data-aos-duration="1000" tag="li" title="А" description="Класс энергоэффективности" />
          <Badge data-aos="zoom-in" data-aos-duration="1500" tag="li" title="42" union="дБ(А)"
            description="Уровень шума" />
          <Badge tag="li" title="4в1" class="badge__title_lowcase" data-aos="zoom-in" data-aos-duration="2000"
            description="Расширенный функционал" />
          <Badge data-aos="zoom-in" data-aos-duration="2500" tag="li" title="Авто" description="Управление жалюзи" />
          <Badge data-aos="zoom-in" data-aos-duration="3000" tag="li" title="Size" description="Компактный размер" />
          <img src="/icon-intro-6.png" alt="" class="about__icon-series" data-aos="zoom-in" data-aos-duration="3000" />
        </ul>
      </div>
    </div>
    <img alt="Мобильный кондиционер Platinum" data-aos="fade-up" data-aos-duration="2000" class="about__image-device"
      src="/device-intro-1.png" />
  </section>

  <Section src="/bg-1.jpg" id="maximum" class="maximum" ref="avto">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Максимум</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">возможностей</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">для вашего комфорта</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text">
        Для большего комфорта мы предусмотрели в мобильном кондиционере серии Platinum все, что
        необходимо для уютной домашней атмосферы. Три уровня интенсивности охлаждения и обогрева,
        автоматический режим работы жалюзи* кондиционера, автоматическое испарение собранного
        конденсата, ночной режим работы и 24-часовой таймер работы прибора.Широкий диапазон
        мощностей мобильных кондиционеров Ballu серии Platinum позволит подобрать прибор,
        максимально соответствующий параметрам помещения, площадью от 18 до 45 м кв. <br> * Автоматические жалюзи в
        моделях BPHS-09H, BPHS-12H
      </p>
    </template>
  </Section>

  <Section src="/bg-2.jpg" right id="silent" ref="silent">
    <template v-slot:title>
      <SectionTitle class="title-item title-item_rigth">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300" data-aos-id="super-duper">Очень
          тихий</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">мобильный</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">кондиционер</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text pros__first-text_right" data-aos="zoom-in" data-aos-once="true">
        Наслаждайтесь прохладным воздухом даже жаркими летними ночами с мобильным кондиционером
        Ballu серии Platinum. Мы поднялись на новый уровень и смогли создать почти невозможное —
        безупречно тихий кондиционер. Громкость работы прибора рекордно низкая в своем классе, всего
        42 дБ(А). Мобильный кондиционер Ballu серии Platinum можно использовать круглосуточно, он
        сохранит воздух свежим и не потревожит ваш сон.
      </p>
    </template>
  </Section>

  <Section src="/bg-3.jpg" id="energo" ref="energoef">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1000">А класс</span>
        <span data-aos="fade-up" data-aos-duration="1500">эффективности</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text text__class-a">
        Мобильный кондиционер Ballu серии Platinum обладет высоким А-классом энергоэффективности.
        Это означает, что прибор отличается очень экономичным расходом электроэнергии и будет
        идеальным решением для охлаждения, даже при небольших возможностях электросети.
      </p>
    </template>
  </Section>

  <Section src="/bg-4.jpg" right>
    <template v-slot:title>
      <SectionTitle class="title-item effect__title">
        <span data-aos="fade-up" data-aos-duration="1000">Эффективный.</span>
        <span data-aos="fade-up" data-aos-duration="1500">работа на обогрев</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text pros__first-text_right">
        Сохраните тепло своего дома с мобильным кондиционером Ballu серии Platinum. Этот прибор
        надежно и эффективно согреет помещение в период холодного межсезонья и в зимние месяцы там,
        где нет центрального отопления или его эффективности не достаточно. Три уровня мощности
        обогрева и управление кондиционером с пульта ДУ подарят легкость и удовольствие от
        использования прибора, а также непревзойденный комфорт вашему дому.
      </p>
    </template>
  </Section>

  <Section src="/bg-5.jpg" id="four">
    <template v-slot:title>
      <SectionTitle class="title-item platinum__title" ref="options">
        <span data-aos="fade-up" data-aos-duration="1000">PLATINUM. 4 В 1 —</span>
        <span data-aos="fade-up" data-aos-duration="1500">КОНДИЦИОНЕР, ОСУШИТЕЛЬ,</span>
        <span data-aos="fade-up" data-aos-duration="2000"></span>
        <span data-aos="fade-up" data-aos-duration="2500">ОБОГРЕВАТЕЛЬ, ВЕНТИЛЯТОР</span>
        <span></span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text">
        Приобретая мобильный кондиционер Ballu серии Platinum вы получаете уникальное устройство,
        сочетающее в себе несколько бытовых климатических приборов. Это мобильный кондиционер для
        жаркого лета там, где невозможно установить классическую сплит-систему. Эффективный
        осушитель воздуха сырой осенью и надежный обогреватель в холодные месяцы.
        Мультифункциональный мобильный кондиционер Ballu серии Platinum круглый год будет вашим
        незаменимым помощником, сохранит бюджет, пространство и истинно комфортную атмосферу вашего
        дома для приятных мгновений с близкими.
      </p>
    </template>
  </Section>

  <section class="compare">
    <SectionTitle class="title-item compare__title">
      <span>ТАБЛИЦА СРАВНЕНИЯ МОДЕЛЕЙ</span>
    </SectionTitle>
    <div class="compare__table">
      <div class="compare-column compare-column_left">
        <Card v-for="card in leftDevicePlatinum" :key="card.model" :card="card" :active="card.model === 'BPHS-09H'">
          <ButtonBuy text="Купить на shop.ballu.ru" tag="a" isForOfficalSite />
          <ButtonBuy text="Купить у  партнеров" tag="a" @click="handleClickFirstBlock"></ButtonBuy>
        </Card>
      </div>
      <div class="compare-column compare-column_right">
        <Card v-for="card in rightDevicePlatinum" :key="card.model" :card="card">
          <ButtonBuy text="Купить на shop.ballu.ru" tag="a" isForOfficalSite />
          <ButtonBuy text="Купить у  партнеров" tag="a" @click="handleClickFirstBlock"></ButtonBuy>
        </Card>
      </div>
    </div>
  </section>
  <section id="parthners" :class="{ 'hidden': isParthnersFirstBlockHidden }">
    <a id="countries"></a>
    <AddressTable @clickCity="selectCity"></AddressTable>
  </section>

  <section class="about" id="smart">
    <img alt="серия smart" class="about__image" src="/bg-intro-2.jpg" />
    <div class="about__text-block smart__text-block">
      <LogoWhite />
      <h2 class="about__title smart__title">
        <span class="about__title-item" data-aos="fade-up" data-aos-duration="1000">Расширяя границы</span>
        <span class="about__title-item" data-aos="fade-up" data-aos-duration="1500">мобильные</span>
        <span class="about__title-item" data-aos="fade-up" data-aos-duration="2000">кондиционеры</span>
        <span class="about__title-item" data-aos="fade-up" data-aos-duration="2500">для дома и бизнеса</span>
      </h2>
      <div>
        <p class="about__subtitle" data-aos="fade-up" data-aos-duration="1000">Мобильный кондиционер</p>
        <div class="about__subtitle-block">
          <p class="about__big-subtitle" data-aos="fade-up" data-aos-duration="1500">серия</p>
          <p class="about__small-subtitle" data-aos="fade-up" data-aos-duration="1500">Smart</p>
        </div>
      </div>
      <ul class="about__badges smart__badges">
        <Badge data-aos="zoom-in-up" data-aos-duration="500" data-aos-delay="300" tag="li" title="А"
          description="Класс энергоэффективности" />
        <Badge data-aos="zoom-in-up" data-aos-duration="500" data-aos-delay="600" tag="li" title="45" union="дБ(А)"
          description="Уровень шума" />
        <Badge tag="li" data-aos="zoom-in-up" data-aos-duration="500" data-aos-delay="900" title="4в1"
          class="badge__title_lowcase" description="Расширенный функционал" />
        <Badge tag="li" title="Авто" description="Управление жалюзи" data-aos="zoom-in-up" data-aos-duration="500"
          data-aos-delay="1200" />
        <Badge tag="li" title="Size" description="Компактный размер" data-aos="zoom-in-up" data-aos-duration="500"
          data-aos-delay="1500" />
      </ul>
    </div>
    <img alt="Мобильный кондиционер Smart" class="about__image-device" data-aos="fade-up" data-aos-duration="2000"
      src="/device-intro-2.png" />
  </section>

  <Section src="/bg-6.jpg" id="3D" ref="threeD">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Интелектуальный</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">3-D воздушный</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">поток</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text">
        Мобильные кондиционеры Ballu серии SMART позволяют регулировать направление воздушного
        потока в четырех направлениях* — вертикальные и горизонтальные жалюзи прибора свободно
        поворачиваются на 180°, равномерно распределяя прохладный воздух по всему помещению в
        автоматическом режиме. <br> * Автоматические жалюзи в моделях BPAC-07 CE_17Y, BPAC-09 CE_17Y, BPAC-12 CE_17Y
      </p>
    </template>
  </Section>

  <Section src="/bg-7.jpg" right id="compact" ref="compact">
    <template v-slot:title>
      <SectionTitle class="title-item compact__title">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Компактный размер</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">в современном дизайне</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text pros__first-text_right">
        Благодаря своим небольшим размерам, мобильные кондиционеры Ballu серии SMART легко и удобно
        использовать для охлаждения небольших помещений, куда крайне неудобно или невозможно
        устанавливать классическую сплит-систему или громоздкие классические мобильные кондиционеры.
        Кондиционеры серии SMART оснащены прочными и подвижными шасси, которые делают приборы очень
        удобными для перемещения по любым напольным покрытиям и установки в необходимое место.
      </p>
    </template>
  </Section>

  <Section src="/bg-8.jpg" id="dry" ref="dry">
    <template v-slot:title>
      <SectionTitle class="title-item mob-cond__title">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Ballu Smart.</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">Больше чем просто</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">кондиционер</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text">
        Мобильный кондиционер Ballu серии SMART - это не только эффективное мобильное охлаждение, но
        и продуктивное осушение воздуха для небольших помещений с повышенной влажностью (до 30
        л/сутки). Несколько режимов вентиляции без дополнительного охлаждения воздуха расширяют
        сферу применения мобильного кондиционера как в городских условиях, так и на даче или в
        хозяйственных целях.
      </p>
    </template>
  </Section>

  <Section src="/bg-9.jpg" right id="night" ref="night">
    <template v-slot:title>
      <SectionTitle class="title-item">
        <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Мобильный кондиционер smart.</span>
        <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">Дополнительные преимущества</span>
      </SectionTitle>
    </template>
    <template v-slot:text>
      <p class="pros__text pros__first-text pros__first-text_right">
        Мы расширили возможности мобильных
        кондиционеров SMART удобными функциями. А-класс энергоэффективности для
        максимальной экономии. Автоматическое испарение конденсата и таймер отложенного старта/выключения для автономной
        работы. Низкий уровень шума 45 дБ(А) и ночной режим для спокойного сна. Интуитивно понятное управление в SMART
        Mechanic и
        пульт ДУ в SMART Electronic.
      </p>
    </template>
  </Section>

  <section class="compare">
    <SectionTitle class="title-item compare__title">
      <span>ТАБЛИЦА СРАВНЕНИЯ МОДЕЛЕЙ</span>
    </SectionTitle>
    <div class="compare__table">
      <div class="compare-column compare__smart-el">
        <Card v-for="card in smartElectronic" :key="card.model" :card="card" :active="card.model === 'BPAC-07 CE_1'"
          class="compare_smart-el-card">
          <ButtonBuy text="Купить на shop.ballu.ru" tag="a" isForOfficalSite />
          <ButtonBuy text="Купить у  партнеров" tag="a" @click="handleClickSecondBlock" href="#countries_smart">
          </ButtonBuy>
        </Card>
      </div>
    </div>
    <div class="parthners" :class="{ 'hidden': isParthnersSecondBlockHidden }">
      <a id="countries_smart"></a>
      <AddressTable @clickCity="selectCity"></AddressTable>
    </div>
    <div class="compare__table">
      <div class="compare-column compare-mechanic-block">
        <Card v-for="card in smartMechanic" :key="card.model" :card="card">
          <ButtonBuy text="Купить на shop.ballu.ru" tag="a" isForOfficalSite />
          <ButtonBuy text="Купить у  партнеров" tag="a" @click="handleClickThirdBlock" href="#countries_smart-mechanic">
          </ButtonBuy>
        </Card>
      </div>
    </div>
    <div class="parthners" :class="{ 'hidden': isParthnersThirdBlockHidden }">
      <a id="countries_smart-mechanic"></a>
      <AddressTable @clickCity="selectCity"></AddressTable>
    </div>
    <div class="compare__table ">
      <div class="compare-column compare-pro__block">
        <Card v-for="card in smartPro" :key="card.model" :card="card">
          <ButtonBuy text="Купить на shop.ballu.ru" tag="a" isForOfficalSite />
          <ButtonBuy text="Купить у  партнеров" tag="a" @click="handleClickForthBlock" href="#countries_smart-pro">
          </ButtonBuy>
        </Card>
      </div>
    </div>
    <div class="parthners" :class="{ 'hidden': isParthnersForthBlockHidden }">
      <a id="countries_smart-pro"></a>
      <AddressTable @clickCity="selectCity"></AddressTable>
    </div>
  </section>

  <section class="other">
    <SectionTitle class="title-item other__title compare__title">
      <span>ДРУГАЯ ПРОДУКЦИЯ BALLU</span>
    </SectionTitle>
    <div class="other__row">
      <OtherItem src="/other-1.png" title="Сушильные мультикомплексы" tag="a" />
      <OtherItem src="/other-2.png" title="Компактные осушитель воздуха" tag="a" />
      <OtherItem src="/other-3.png" title="Компактные осушители воздуха" tag="a" />
    </div>
    <div class="other__row">
      <OtherItem src="/other-4.png" title="Стандартные осушители воздуха" tag="a" />
    </div>
  </section>

  <footer class="footer">
    <div class="footer__social">
      <a class="footer__link-vk" href="https://vk.com/ballu.official" target="_blank"></a>
    </div>
    <div class="footer__copy">
      <p>Copyright &copy; 2023</p>
      <a href="https://www.ballu.ru/" class="footer__site-link">Ballu</a>
      <p>Все права защищены. Условия использования и политика конфиденциальности</p>
    </div>
  </footer>

  <ParthnersPopup :class="{ 'hidden': !isPopupOpen }" :selectedCity="currentCity" @close="closePopup"></ParthnersPopup>
</template>

<style scoped></style>
