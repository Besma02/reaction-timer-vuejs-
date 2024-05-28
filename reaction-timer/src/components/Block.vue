<template>
  <div class="block" v-if="showedBlock" @click="stopTimer">
    <h1>click me</h1>
  </div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return{
            showedBlock:false,
            timer:null,
            reactionTimer:0
        }
    },
    mounted(){
      
       setTimeout(()=>{
        this.showedBlock=true
        this.startTimer()
       },this.delay)
      
    },
    methods:{
        startTimer(){
            this.timer=setInterval(()=>{
             this.reactionTimer+=10
            },10)

        },
        stopTimer(){
         clearInterval(this.timer)
         this.$emit('end',this.reactionTimer)
        }
    }
   

}
</script>

<style>
.block{
    width: 500px;
    text-align: center;
    background: #0faf87;
    padding: 100px 0;
    margin: 40px auto;
    border-radius: 20px;
    color:#fff
}

</style>