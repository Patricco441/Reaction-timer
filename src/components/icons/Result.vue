
<template>
  <div class="Result">
   
    <p>your reaction time is {{ score }} ms  </p>
    <p class="rank">{{ rank }}</p>

 
  </div>
</template>

<script>
export default {
  name: 'Result',
  created() {

  },
  data() {
    return {
      rank:null
    }
  },
  props: [
   'score',
   'ShowReaction',
   'reactiontime',
 ],
 mounted(){
    if(this.score<250)
    {
      this.rank='fast reaction'
    }
    else if(this.score <400)
    {
      this.rank='medium reaction'
    }
    else {
      this.rank='snail pace'
    }


    
 },
  methods: {
   
  },
}
</script>

<style  scoped>

.rank{
font-size:1.4rem;
color:rgb(107, 70, 76);
font-weight: bold;
}

</style>

