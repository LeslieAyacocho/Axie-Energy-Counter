<template>

<div class="container">
  <!-- <div class="blank"></div> -->
  <div class="row">
    <div class="col-sm-2">
    
    </div>
    <div class="col-sm-6">
      <div class="card"> 
        <Round :roundNum="roundNum"/>

        <div class="counter">
            <div class="energyContainer">
                <button class="add" @click="add">+</button>
                <h1>{{energy}} / 10</h1>  
                <button class="minus" @click="minus">-</button>
            </div>
            <div class="counterButtons">
                
                <button class="nextRound" @click="nextRound" style=" width:67%">Next Round</button>
                <button class="reset" @click="reset" style=" width:26%">Reset</button>
            </div>
            <img src="./assets/img/puff-in-bucket.gif" alt="" v-show="!curse">
            <Bloodmoon :bloodmoon="bloodmoon" v-show="curse"/>
        </div>
      </div>
    </div>

    <div class="col-sm-1">
      <div class="tools">
        <button class="arena"  @click="showLogs"><img src="./assets/img/pvp.png" alt=""> </button>
        <button class="triangle" @click="showTri"><img  src="./assets/img/triangle.png" alt=""></button>
      </div>
    </div>

    <div class="col-sm-1">
        <div class="toolsPage">
          <div class="arenalog" v-show="arenaLogs" style="" >
            <Arena/>
          </div>

          <div class="axietriangle" style=" "  v-show="showTriangle">
            <img src="./assets/img/triangle.png" alt="">
          </div>
      </div>
    </div>
  </div>

</div>
<Footer/>
</template>

<script>
import Round from './components/Round.vue';
import Bloodmoon from './components/Bloodmoon.vue'
import Footer from './components/Footer.vue'
import Arena from './components/Arena.vue'

export default {
  name: 'App',
  data(){
    return{
      roundNum:1,
      energy:3,
      bloodmoon:50,
      curse: false,
      showTriangle: false,
      arenaLogs: false,
    }
  },
  components: {
    Round,
    Bloodmoon,
    Footer,
    Arena
  },
  methods:{
    nextRound(){
      ++this.roundNum
      if(this.energy < 10){
        if (this.energy == 9){
        this.energy = this.energy + 1
        }
        else{
          this.energy= this.energy + 2
        }
      }

      if(this.roundNum == 10){
          this.curse=true
      }
      if(this.roundNum > 10){
        this.bloodmoon = this.bloodmoon + 30
      }
      
      
      
    },
    reset(){
      this.roundNum = 1
      this.energy = 3
      this.bloodmoon = 50
      this.curse= false
    },
    add(){
      if(this.energy < 10){
        ++this.energy
      }
      
    },
    minus(){
      if(this.energy > 0){
      --this.energy
      }
    },
    showTri(){
      this.showTriangle = !this.showTriangle
      if(this.arenaLogs = true){
        this.arenaLogs = false
      }
    },
    showLogs(){
      this.arenaLogs = !this.arenaLogs
      if(this.showTriangle = true){
        this.showTriangle = false
      }
    }
    

  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Changa+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
body{
  background: #383838;
  overflow:visible;
}
#app {
  font-family: 'Changa One', cursive;
  font-family: 'Robot Bold', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 !important;
  
}
.tools{
  margin-top:130px;
  
}
.tools button{
  display: block; 
  width: auto;
  margin:10px;
  padding: 5px;
  background: #E7FFFF;
  border-radius: 10px;
  border: solid 3px #11A4CC;
}

.tools img{
  width: 50px;
  
}

.toolsPage{
  position: inherit; 
  display: inline-block;
  padding:0px;
  margin-top:130px;
  margin-right:-300px;
  float:left;
}

.arenalog{
  width:300px;
  min-height: 300px;
  background: #F9A802;
  border-radius:10px;
}
.axietriangle img{
  margin:0;
  padding:10px;
  width: 280px;
  background: #E7FFFF;
  border-radius:10px;
}
@media (max-width: 1200px) {
  .card{
    margin: 0;
  }
  .tools{
    width:100%;
    margin-top: 0px;
    align-content: center;
  }
  .tools button{
    display: inline-block !important;
  }
  .toolsPage{
  margin-top: 0px;
  display: block;
  padding: 0 20%;
}
}

.container{
  display: inline-block;
}
.card{
  display: inline-block;
  width: 500px;
  height: 650px;
  margin: auto;
  align-items: center;
  background:#2F525E;
  border-radius: 30px;
}

.counter{
    float:center;
    margin: 4% 4% 0 4%;
    align-items: center;
    height: 95%;
    background: #3A7BBA;
    border-radius: 30px;
}
.counter button{
    font-family: 'Changa one', cursive;
}

.counter img{
    width: 225px;
    padding:10px
    
}
.energyContainer{
    padding: 120px 0 0 0;
}
.energyContainer button{
    height: 150px;
    width: 100px;
    font-size:90px;
    color: #E7FFFF;
    background: #11A4CC;
    border: 0;
    border-radius: 5px;
}

button.nextRound:hover{
    color: #E7FFFF ;
    background: #F9A802;
}
button.add:hover{
    background:#67e68d;
}
button.minus:hover, button.reset:hover{
    background:#e66767;
}

.energyContainer h1{
    font-family: 'Changa One', cursive;
    margin: -30px 0 -40px 0;
    font-size:70px;
    font-weight: 100;
    display: inline-block;
    min-width:235px;
    color: #E7FFFF;
    text-shadow: 2px 2px #383838;
}
.counterButtons button{
    height: 70px;
    margin: 20px 1% 0 1%;
    font-size:30px;
    font-weight: 100;
    color: #E7FFFF;
    background: #11A4CC;
    border: 0;
    border-radius: 5px;
}

.row{
  margin: 0;
}
</style>
