<template>
   <div>
  <h1>Reaction-timer</h1>
   <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <result v-if='showResult' :score="score" />
  </div>
</template>

<script>
import Block from'./components/Block.vue'
import Result from './components/Result.vue'
export default {
  components:{
    Block,
    Result
  },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:null,
      showResult:false
    }
  },
  methods:{
    start(){
      this.isPlaying=true,
      this.delay=2000+Math.random()*5000
      showResult:false
    },
    endGame(reactionTimer){
      this.score=reactionTimer
      this.showResult=true
    }
  }

}
</script>

<style>
#app{
  text-align: center;
}
button{
  background:#0faf87;
  color:white;
  cursor: pointer;
  border-radius: 4px;
  border: none;
  margin: 10px;
  font-size: 16px;
  padding: 10px;

}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>