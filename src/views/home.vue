<template>
  <div class="bg-gradient-to-b from-white to-slate-100">
    <HeroBanner />
    
  </div>
</template>

<script>
import Opportunities from '../components/Opportunities.vue';
import HeroBanner from '../components/HeroBanner.vue'
import OurMission from '../contents/OurMission.vue';

export default {
  components: { HeroBanner,  OurMission, Opportunities },
}
</script>

<style>
</style>
