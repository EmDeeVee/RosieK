<script setup>
    import CtaButton from "./CtaButton.vue"
</script>

<template>
    <div class="absolute z-30">
        <img src="../assets/DinoRosieKSubQuestion.png" alt="" class="rounded-3xl shadow-slate-900 shadow-2xl drop-shadow-2xl">
        <div class="absolute bottom-0 mb-12 grid grid-cols-12  w-full">
            <!-- buttons-->
            <CtaButton label="Yes, Keep me posted!" dest="#/subscribe" class="col-start-2 col-span-10 mb-8"/>
            <CtaButton label="No thanks, take me to the Store" dest="https://www.redbubble.com/people/RosieDino32/shop" class="col-start-2 col-span-10 mb-8"/>
        </div>
    </div>
</template>