

<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
   click me
  </div>
</template>

<script>
export default {
  name: 'Block',
  created() {

  },
  data() {
    return {
      showBlock:false,
      timer:null,
      reactionTime:10
    }
  },
  props: ['Delay'],
  mounted(){

    setTimeout(()=>{
      this.showBlock = true
      this.startTimer( )


    },this.Delay)

  },

  updated(){

  },
  methods:{
    startTimer(){
      this.timer=setInterval(()=>{
        this.reactionTime+=10
      },10)

    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end',this.reactionTime)

      console.log(this.reactionTime);
    }
  }



}
</script>

<style  scoped>


.block{
  width:400px;
  border-radius: 20px;
  background-color: green;
  text-align: center;
  color:white;
  padding:100px 0;
  margin:40px auto;
}

</style>

