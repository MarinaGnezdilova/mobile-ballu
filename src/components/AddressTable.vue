<script setup lang="ts">
import { ref } from 'vue';
import { citiesRus, citiesArm, citiesBel, citiesCyp, citiesGeog, citiesKaz, citiesLat, citiesLit, citiesMold, citiesTadj, citiesUzb } from '@/mock/cities';
import { alfAr } from '@/constant/alf';

function resCities(ar:Array<string>, alf:Array<string>) {
  let sortCities = ar.sort();
  let fullArray = [];
  for (let i = 0; i < alf.length; i++) {
    fullArray[i] = sortCities.filter((el) => el[0].toLowerCase() === alf[i])
  }
  return fullArray.filter((el) => el.length > 0);
}

const citiesArRus = resCities(citiesRus, alfAr);
const citiesArArm = resCities(citiesArm, alfAr);
const citiesArBel = resCities(citiesBel, alfAr);
const citiesArCyp = resCities(citiesCyp, alfAr);
const citiesArGeog = resCities(citiesGeog, alfAr);
const citiesArKaz = resCities(citiesKaz, alfAr);
const citiesArLat = resCities(citiesLat, alfAr);
const citiesArLit = resCities(citiesLit, alfAr);
const citiesArMol = resCities(citiesMold, alfAr);
const citiesArTadj = resCities(citiesTadj, alfAr);
const citiesArUzb = resCities(citiesUzb, alfAr);
const countries = ref([
  {
    country: 'pоссия',
    isCountryActive: true,
    cities: citiesArRus
  },
  {
    country: 'армения',
    isCountryActive: false,
    cities: citiesArArm
  },
  {
    country: 'беларусь',
    isCountryActive: false,
    cities: citiesArBel
  },
  {
    country: 'грузия',
    isCountryActive: false,
    cities: citiesArGeog
  },
  {
    country: 'казахстан',
    isCountryActive: false,
    cities: citiesArKaz
  },
  {
    country: 'латвия',
    isCountryActive: false,
    cities: citiesArLat
  },
  {
    country: 'литва',
    isCountryActive: false,
    cities: citiesArLit
  },
  {
    country: 'молдова',
    isCountryActive: false,
    cities: citiesArMol
  },
  {
    country: 'республика кипр',
    isCountryActive: false,
    cities: citiesArCyp
  },
  {
    country: 'таджикистан',
    isCountryActive: false,
    cities: citiesArTadj
  },
  {
    country: 'узбекистан',
    isCountryActive: false,
    cities: citiesArUzb
  },
]);

function hadleClick(event: Event) {
  let currentCountryIndex = countries.value.findIndex(el => el.isCountryActive === true);
  countries.value[currentCountryIndex].isCountryActive = false;
  let clickCountryIndex = countries.value.findIndex(el => el.country === (event.target as HTMLInputElement).innerText.toLowerCase());
  countries.value[clickCountryIndex].isCountryActive = true;
}
const emit = defineEmits(['clickCity']);

</script>
<template>
  <div class="pathners__block">
    <div class="contries">

      <div class="countries__country" v-for="country in countries" :key="country.country" @click="hadleClick"
        :class="{ 'countries__country_active ': country.isCountryActive }">
        {{ country.country }}
      </div>
    </div>
    <div class="cities__block" v-for="country in countries" :key="country.country"
      :class="{ 'hidden': !country.isCountryActive }">
      <div class="cities">
        <div v-for="(item, index) in country.cities" class="cities__letter-block" :key="index">
          <p class="cities__letter">{{ item[0][0] }}</p>
          <ul class="cities__list">
            <li v-for="(city, index) in item" class="cities__city" @click="$emit('clickCity', city)" :key="index">
              {{ city }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
