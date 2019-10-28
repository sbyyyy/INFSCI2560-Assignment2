<template>
    <div v-if="player!=null">
      <h1>
          {{player.name}}
      </h1>
      <img :src="player.pic" alt="cannot load" height="450px" width="800px">
      <p>
          {{player.description}}
      </p>
    </div>
</template>

<script>
import { bus } from '../main'
export default {
    data(){
        return{
            player: null
        }
    },
    mounted(){
        bus.$on('showPlayer',(p)=>{
            this.player=p
        })
    }   
}
</script>

<style scoped>
.a{
    margin-top: 10px
}
</style>