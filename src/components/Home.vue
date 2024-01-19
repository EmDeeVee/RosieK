<script setup>
    import Slider from "./Slider.vue";
    import CtaButton from "./CtaButton.vue"
</script>

<template>
    <div class="absolute z-30">
        <img src="../assets/DinoRosieKAd.png" alt="" class="rounded-3xl shadow-slate-900 shadow-2xl drop-shadow-2xl">
        <div class="absolute bottom-0 mb-8 grid grid-cols-5 gap-4 w-full">
            <div></div>
            <CtaButton id='subscribe' label="Subscribe" />
            <div></div>
            <CtaButton id='visit' label="Visit my Store" />
            <div></div>
        </div>
    </div>
    <Slider />
</template>