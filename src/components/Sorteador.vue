<template>
  <div>
    <p class="description">Sorteador de rolês incríveis para fazermos juntinhos</p>
    <div :class="{
      'winner': winnerIndex !== null,
      'loading': isLoading,
      'possibility': true,
      'hidden': isHidden
    }">
    <p>
      {{ currentPossibility }}
    </p>
    </div>
    <div class="button-gamble">

<div @click="gamble" :class="{pixel: true, 'pixel-disabled':isLoading}"><p>Sortear Novo Rolê</p></div>
<audio preload="auto" ref="audioLoading">
            <source src="../assets/spinning-wheel.mp3" type="audio/mpeg">
          </audio>
</div>
  </div>
</template>
<script>
export default {
  name: 'Sorteador',
  props: {
    handleGambled: Function
  },
  data() {
    return {
      possibilities: [
        "Jardim Botânico",	
        "Pique nique na UF",
        "Sushi",
        "Pizza",
        "Barzinho",
        "Pub",
        "Tomar cogu",
        "Planejar viagem",
        "Cinema",
      ],
      winnerIndex: null,
      isLoading: false,
      isHidden: true,
      loadingDuration: 9, // seconds
      currentPossibility: null,
    }
  },
  created() {
    this.currentPossibility = this.possibilities[Math.floor(Math.random() * this.possibilities.length)]
  },
  methods: {
    gamble(){
      this.isHidden = false
      if(this.isLoading) return
      this.isLoading = true
      this.$refs.audioLoading.play()
      this.handleGambled()
      this.winnerIndex = Math.floor(Math.random() * this.possibilities.length)
      this.currentPossibility = this.possibilities[Math.floor(Math.random() * this.possibilities.length)]
      const updateItemInterval = setInterval(() => {
        this.currentPossibility = this.possibilities[Math.floor(Math.random() * this.possibilities.length)]
      }, 100)
      setTimeout(() => {
        clearInterval(updateItemInterval)
        this.isLoading = false
        this.currentPossibility = this.possibilities[this.winnerIndex]
      }, this.loadingDuration * 1000)
    }
  }	
}
</script>
<style scoped>
.description{
  padding: 0 30px;
  font-size: 1.1rem;
  text-align: center;
}
.possibility{
  font-size: 24px;
  font-weight: bold;
  text-align: center;
  padding: 20px;
  color: #ddd;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin: 20px;
}
  .loading {
    filter: blur(3px);
  }
  .hidden{
    opacity: 0;
  }
  .button-gamble{
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>