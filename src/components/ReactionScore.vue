<template>
  <p class="score">{{ score }}</p>
  <h3 class="rank">{{ rank }}</h3>
</template>

<script>
export default {
props:['score'],
data() {
    return {
        rank: null,
    }
},
mounted () {
    if(this.score < 260){
        this.rank= "Sayar Gyi"
    }else if(this.score <400){
        this.rank = "OK BUT"
    }else this.rank = "Noob!!!!!!!!!"
}   
}
</script>

<style>

</style>