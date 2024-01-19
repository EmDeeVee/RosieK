<template>
    <div>
      <transition-group name="fade" tag="div">
        <div v-for="i in [currentIndex]" :key="i">
          <img :src="currentImg" />
        </div>
      </transition-group>
    </div>
</template>

<script>
  export default {
    name: "Slider",
    data() {
      return {
        images: [
            "/BlubDinoMsk.png",
            "/BookLoverMsk.png",
            "/GilbertMsk.png",
            "/HuggingRex-iesMsk.png",
            "/BlubFishMsk.png",
            "/PatTeraDactieMsk.png",
            "/GhostyDinoMsk.png",
            "/SquidMsk.png",
            "/PandaInABoxMsk.png",
            "/SleepyPuppyMsk.png",
            "/GnomeShittingMsk.png",
            "/LittleOctopusMsk.png",
            "/RosieDinoLogoMsk.png",
        ],
        timer: null,
        currentIndex: 0
      };
    },
  
    mounted: function() {
      this.startSlide();
    },
  
    methods: {
      startSlide: function() {
        this.timer = setInterval(this.next, 2000);
      },
  
      next: function() {
        this.currentIndex += 1;
      },
    },
  
    computed: {
      currentImg: function() {
        return this.images[Math.abs(this.currentIndex) % this.images.length];
      }
    }
  };
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width:100%;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width:100%;
  opacity: 0;
}
</style>