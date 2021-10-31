<template>
 <div id='cloudy'>
   <h1>The weather at Central Saint Martins is: <div id="desc_text">{{description}}</div></h1>
   <h1>The Temperature is:<div id="desc_text"> {{temperature}} °C</div></h1>
   <h1>The Windspeed is: <div id="desc_text">{{windspeed}} km/h</div></h1>
   <img id="image" src="../assets/cloudy/1.png" />
 </div>
</template>
 
<script>
export default {
// data taken from Api Call in App.vue
 props: ['description','temperature', 'windspeed']
}
</script>
<style lang="scss"  scoped>
#cloudy{
font-family: monospace;
text-align: center;
border-color: blue;
width: 90%; //fallback
width: 90vw;
height: 70vh;
    #desc_text{
        //font-size: 5vw;
        font-size: 5vh;
        font-family: Cloudy;
        color: rgb(62, 62, 62);
    }
}
#image{
    width: 50vw;
}
</style>
