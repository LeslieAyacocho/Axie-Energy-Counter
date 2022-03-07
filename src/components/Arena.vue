<template>
    <div class="arena ">
        <div class="group">
            <label for="">WIN</label><br>
            <button type="button" class="add" @click="addWin">+</button>
                <p>{{win}}</p>
            <button class="minus" @click="minusWin">-</button>
        </div>
        <div class="group">
            <label for="">LOSE</label><br>
            <button type="button" class="add" @click="addLose">+</button>
                <p>{{lose}}</p>
            <button class="minus" @click="minusLose">-</button> <br>
        </div>
        <div class="group">
            <label for="">DRAW</label><br>
            <button type="button" class="add" @click="addDraw">+</button>
                <p>{{draw}}</p>
            <button class="minus" @click="minusDraw">-</button> <br>
        </div>
        <div class="reset">
        <button type="button" class="reset" @click="resetTally">Reset</button>
        </div>
    </div>
</template>

<script>
export default {
data(){
    return{
        win: 0,
        lose: 0,
        draw: 0
    }
},
methods:{
    addWin(){
        if(this.win >= 0){
            ++this.win
        }
    },
    minusWin(){
        if(this.win > 0){
            --this.win
        }
    },
    addLose(){
        if(this.lose >=0){
            ++this.lose
        }
    },
    minusLose(){
        if(this.lose > 0){
            --this.lose
        }
    },
    addDraw(){
        if(this.draw >= 0){
        ++this.draw
        }
    },
    minusDraw(){
        if(this.draw > 0){
        --this.draw
        }
    },
    resetTally(){
        this.win = 0
        this.lose = 0
        this.draw = 0
    }
}
}
</script>

<style>

.group{
    padding: 3px;
}
.group button{
    font-family: 'Changa One', cursive;
    font-weight: 100px;
    font-size:20px;
    height: 50px;
    width: 40px;
    color: #E7FFFF;
    background: #11A4CC;
    border-radius: 5px;
    border: none;
}

.reset button{
    font-family: 'Changa One', cursive;
    /* font-weight: 100px; */
    font-size:20px;
    border: none;
    width: 110px;
    color: #E7FFFF;
    background: #11A4CC;
    border-radius: 5px;
    padding: 3px;
    margin: 5px;
}
.group p{
    font-family: 'Changa One', cursive;
    font-weight: 100px;
    display: inline-block; 
    width: 30px;
}

.group label{
    font-family: 'Changa One', cursive;
    font-weight: 100px;
    font-size: 20px;
    margin: 0;
    color: #E7FFFF;
    text-shadow: 2px 1px #383838;
}


</style>