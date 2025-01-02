<template>
  <div>
  <header v-if="gambledTimes<2">
    <logo></logo>
  </header>
  <main>
    <sorteador :handleGambled="gambled" v-if="gambledTimes<2"></sorteador>
    <dating-propose v-else></dating-propose>
  </main>
  <footer v-if="gambledTimes<2">
    <footer-comp></footer-comp>
  </footer>
  </div>
</template>
<script>
import Logo from './components/Logo.vue'
import Sorteador from './components/Sorteador.vue'
import DatingPropose from './components/DatingPropose.vue'
import FooterComp from './components/Footer.vue';

export default {
  name: 'MainPage',
  components: {
    Logo,
    Sorteador,
    DatingPropose,
    FooterComp
  },
  data() {
    return {
      gambledTimes: 0
    }
  },
  mounted() {
    this.preloadAudios()
  },
  methods: {
    gambled(){
      this.gambledTimes++
    },
    preloadAudios(){
      const audios = [
        '../assets/yes-sound.mp3',
        '../assets/spinning-wheel.mp3'
      ]
      audios.forEach(audio => {
        fetch(audio)
      })
    }
  }
}
</script>
<style scoped>
  
header{
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
footer{
  position: absolute;
  bottom: 0;
  display: flex;
  padding: 30px;
  font-size: 0.7rem;
}
</style>