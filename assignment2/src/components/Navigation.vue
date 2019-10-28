<template>
  <div class="navBackground">
    <h1 style="color:white">
      My favourite soccer team---liverpool
    </h1>
    <div style="display:flex;margin-bottom:0">
      <div class="player" v-for="(p,i) in players" :key="i" @click="choosePlayer(p)">
        <p>
          {{p.name}}
        </p>
      </div>
    </div>
    
  </div>
</template>

<script>
import { bus } from '../main'
export default {
  data () {
    return {
      players:[
        {
          name: 'Salah',
          pic:'https://cdn.cnn.com/cnnnext/dam/assets/190501145802-mo-salah-exlarge-169.jpg',
          description:'Mohamed Salah Hamed Mahrous Ghaly (Arabic: محمد صلاح حامد محروس غالى‎, Egyptian Arabic pronunciation: [mæˈħam.mæd sˤɑˈlɑːħ ˈɣæːli]; born 15 June 1992) is an Egyptian professional footballer who plays as a forward for Premier League club Liverpool and the Egypt national team. Considered one of the best players in the world,[6][7][8] he is known for his finishing, dribbling, and speed.'
        },
        {
          name: 'Mane',
          pic:'https://s.yimg.com/ny/api/res/1.2/JY7mmf9uKKPTkwBau_8vnQ--~A/YXBwaWQ9aGlnaGxhbmRlcjtzbT0xO3c9ODAw/http://media.zenfs.com/en-US/homerun/nbcsports.com/b4c89e83534730e24c965b055acc951e',
          description:'Sadio Mané is a Senegalese professional footballer who plays as a winger for Premier League club Liverpool and the Senegal national team. Having begun his career with Metz in France, he transferred to Red Bull Salzburg in 2012.'
        },
        {
          name: 'Van Dijk',
          pic:'https://www.sundaypost.com/wp-content/uploads/sites/13/2018/04/5adb4c5d07cb6-e1524321806466.jpg',
          description:'Virgil van Dijk (Dutch pronunciation: [vɑn ˈdɛik]; born 8 July 1991) is a Dutch professional footballer who plays as a centre-back for English Premier League club Liverpool and captains the Netherlands national team. Considered to be one of the best defenders in the world, he is known for his strength, leadership and aerial ability. In 2019 he was named the UEFA Mens Player of the Year; he also finished as runner-up for The Best FIFA Mens Player.'
        }
      ]
    }
  },
  methods:{
    choosePlayer(player){
      bus.$emit('showPlayer',player)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navBackground{
  background-color: #8a1127;
  height: 100px;
  width: 100%;
  margin: 0;
  padding-left:10%;
}
.player{
  color: white;
  margin-right:10px;
}
.player:hover{
  color:yellow;
}
</style>
