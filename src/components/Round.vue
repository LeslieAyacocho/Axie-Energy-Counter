<template>
    <div class="round">
        <img alt="Round number" src="../assets/img/Banner.png">
        <h2>Round {{roundNum}}</h2>
    </div>
</template>

<script>
export default {
    props: ['roundNum'],
}
</script>

<style>
.round img{
    margin: 10px 10px 0 10px ;
    width:90%;
}
.round h2 {
    font-family: 'Changa One', cursive;
    margin: -95px;
    font-size:50px;
    font-weight: 100;
    color: #E7FFFF;
    text-shadow: 2px 2px #383838;
}
</style>