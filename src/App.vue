

<template>

<h1>Reaction Timer</h1>
<button  class="buttonik" @click="start" :disabled="isPlaying">Play</button>
<Block v-if="isPlaying" :Delay="Delay" @end="endGame" /> 
<Result  v-if="ShowReaction" :score="score"/> 

</template>


<script >
import Block from './components/icons/Block.vue';
import Result from './components/icons/Result.vue';
export default {
  name:'App',
  components:{
    Block,
    Result,
    

  },
  data(){
    return{
      isPlaying:false,
      Delay:null,
      score: null,
      ShowReaction:false

    }
  },

  methods:{
    start(){
      this.Delay=2000 + Math.random()  * 5000
      this.isPlaying=true
      this.ShowReaction=false
  },
  togglePlay(){
    this.isPlaying=!this.isPlaying
  },
  endGame(reactionTime){
    this.score=reactionTime
    this.isPlaying=false
    this.ShowReaction=true

},
  }
}



</script>

<style >

#app {
  text-align: center;
  color:rgb(107, 70, 76);
  margin-top: 60px;



}
.buttonik{
  margin:10px;
  padding:10px;
  color:white;
  border:none;
  border-radius: 5px;
  background-color: rgb(88, 129, 22);
  letter-spacing: 1px;
  font-size: 25px;
  cursor: pointer;

}

.buttonik[disabled]
{
  cursor:not-allowed;
  opacity: 0.25;
}
</style>
