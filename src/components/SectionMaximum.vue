<script setup lang="ts">
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<template>
    <Section src="/bg-1.webp" id="maximum" class="maximum">
        <template v-slot:title>
            <SectionTitle class="title-item">
                <span data-aos="fade-up" data-aos-duration="1500" data-aos-delay="300">Максимум</span>
                <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="600">возможностей</span>
                <span data-aos="fade-up" data-aos-duration="1000" data-aos-delay="900">для вашего комфорта</span>
            </SectionTitle>
        </template>
        <template v-slot:text>
            <p class="pros__text">
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
</template>

<style>
.pros__text {
    display: block;
    font-size: 1.3em;
    line-height: 1.2;
    margin-top: 15px;
    width: 48%;
    margin-top: 30px;
}

@media screen and (max-width: 1650px) {
    .pros__text {
        display: block;
        background-color: rgb(255, 255, 255, 0.7);
    }
}

@media screen and (max-width: 1280px) {
    .pros__text {
        font-size: 1em;
        width: 100%;
    }
}

@media screen and (max-width: 950px) {
    .pros__text {
        font-size: .85em;
        color: #0c0d0d;
    }
}

@media screen and (max-width: 750px) {
    .pros__text {
        font-size: .65em;
    }
}

@media screen and (max-width: 500px) {
    .pros__text {
        font-size: .55em;
        margin-top: 5px;
    }
}

@media screen and (max-width: 500px) {
    .pros__text {
        font-size: .45em;
    }
}</style>