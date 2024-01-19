<script setup>
    import Slider from "./components/Slider.vue";
    import CtaButton from "./components/CtaButton.vue"
</script>

<template>
     <section class="flex justify-center items-center">
        <div id="frame" class="container mt-6 justify-center max-w-screen-md relative">
            <div class="absolute z-30">
                <img src="./assets/DinoRosieKAd.png" alt="" class="rounded-3xl shadow-slate-900 shadow-2xl drop-shadow-2xl">
                <div class="absolute bottom-0 mb-8 grid grid-cols-5 gap-4 w-full">
                    <div></div>
                    <CtaButton label="Subscribe" />
                    <div></div>
                    <CtaButton label="Visit my Store" />
                    <div></div>
                </div>
            </div>
            <Slider />
        </div>
    </section>
</template>

