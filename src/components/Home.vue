<script setup>
    import Slider from "./Slider.vue";
    import CtaButton from "./CtaButton.vue"
</script>

<template>
    <div class="absolute z-30">
        <img src="../assets/DinoRosieKAd.png" alt="" class="rounded-3xl shadow-slate-900 shadow-2xl drop-shadow-2xl">
        <div class="absolute bottom-0 mb-8 grid grid-cols-12 gap-2 w-full">
            <CtaButton id='subscribe' label="Subscribe" dest="#/subscribe" class="col-start-2 col-span-4"/>
            <CtaButton id='visit' label="Visit my Store" dest="#/question" class="col-start-8 col-span-4"/>
        </div>
    </div>
    <Slider />
</template>