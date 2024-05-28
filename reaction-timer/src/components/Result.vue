<template>
<div>
  <p>reactionTime:{{ score }}ms</p>
  <div class="rank">{{ rank }}</div>
</div>
  
</template>

<script>
export default {
    props:['score'],
    data(){
        return{
            rank:null
        }
    },
    mounted(){
        if(this.score<250){
            this.rank='fingers crossed'
        }
        else if(this.score<400){
            this.rank='rapid reflex'
        }
        else{
            this.rank='snaill pace ..'
        }
    }

}
</script>

<style>
.rank{
    font-size: 1.4em;
    font-weight: bold;
    color:#0faf87
}
</style>