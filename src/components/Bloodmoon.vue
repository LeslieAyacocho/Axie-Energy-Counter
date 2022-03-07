<template>
    <div class="bloodmoon">
        <h4>Bloodmoon Curse</h4>
        <h3> - {{bloodmoon}} hp</h3> 
    </div>
</template>

<script>
export default {
    props:['bloodmoon'],
}
</script>

<style>
.bloodmoon{
    padding: 5px;
    
    color:#E7FFFF;
    background: #e66767;
    margin:10px;
    border-radius: 10px;
}

.bloodmoon h4{
    font-size:30px;
    font-weight:100;
    margin:20px;
}

.bloodmoon h3{
    font-size:50px;
    font-weight:100;
    margin:20px;
}
</style>