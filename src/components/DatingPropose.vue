<template>
  <div>
    <div class="header">
      <img src="../assets/warning.png" alt="">
      <p>ATENÇÃO</p>
    </div>
    <div class="propose">
      <p>Como ja te disse inúmeras vezes, eu ainda não consigo acreditar que encontrei você, a mulher dos meus sonhos, que curte as mesmas coisas que eu, que é simplesmente uma deusa de tão linda. Esse site é só uma pequena forma de comprovar isso, eu faria todos esses rolês e mais infinitos outros com você, meu amor.<br><br>Por isso e por mais infinitos motivos, eu quero ficar ao seu lado todos os dias a partir de hoje, eu definitivamente não consigo mais ficar longe de você. <strong>EU TE AMO!!!</strong>  </p>

      <div v-if="!isHidden">
        <p class="question">Quer namorar comigo?</p>
        <div class="options">
          <div @click="saidYes" :class="{pixel: true}"><p>Sim</p></div>
          <audio preload="auto" ref="audioYes">
            <source src="../assets/yes-sound.mp3" type="audio/mpeg">
          </audio>
        </div>
      </div>
    </div>
    <div class="heart heart-1">
      <img src="../assets/small-heart.gif">
    </div>
    <div class="heart heart-2">
      <img src="../assets/small-heart.gif">
    </div>
    <div class="heart heart-3">
      <img src="../assets/small-heart.gif">
    </div>
    <div class="heart heart-4">
      <img src="../assets/small-heart.gif">
    </div>
    <div class="heart heart-5">
      <img src="../assets/small-heart.gif">
    </div>
    <div class="heart heart-6">
      <img src="../assets/small-heart.gif">
    </div>

  </div>
</template>
<script>
export default {
  name: 'DatingPropose',
  data() {
    return {
      isHidden: true,
      saidYesMusic: false
    }
  },
  methods: {
    saidYes(){
      this.$refs.audioYes.play()
      setTimeout(() => {
        alert('Eu te amo muito, meu amor!!!')
      }, 0.5 * 1000)
      
    }
  },
  created() {

    setTimeout(() => {
      this.isHidden = false
    }, 15 * 1000)
  },
  mounted() {

    
  },

}
</script>
<style scoped>
.heart{
  height: 60px;
  display: flex;
  position: absolute;
}
.heart-1{
  top: 10px;
  right: 10px;
}
.heart-2{
  bottom: 100px;
  right: 12px;
}
.heart-3{
  bottom: 150px;
  left: 25px;
}
.heart-4{
  bottom: 250px;
  left:200px;
}
.heart-5{
  bottom: 260px;
  right:10px;
  height: 50px;
}
.header{
  display: flex;
  align-items: center;
  margin-bottom: 5px;

}
  .header img{
    height: 110px;
    margin-right: -20px;
  }
  .header p{
    font-size: 40px;
  }
  .propose{
    font-family: 'Karla', sans-serif;
    padding: 5px 30px;
    font-size: 15px;
    margin-top: -60px;
  }
  .question{
    font-family: 'Pixelify Sans';
    font-size: 30px;
    text-align: center;
  }
  .options{
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
