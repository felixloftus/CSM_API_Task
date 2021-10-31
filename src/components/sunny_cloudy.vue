<template>
 <div id='sunny_cloudy'>
   <h1>The weather at Central Saint Martins is: <div id="desc_text">{{description}}</div></h1>
   <h1>The Temperature is: <div id="desc_text">{{temperature}} °C</div></h1>
   <h1>The Windspeed is: <div id="desc_text">{{windspeed}} km/h</div></h1>
   <img id="image" src="../assets/sunny_cloudy/sunny_cloudy.jpeg" />
 </div>
</template>
 
<script>
export default {
 props: ['description','temperature', 'windspeed']
}
</script>
<style lang="scss"  scoped>
#sunny_cloudy{
//background-color: rgb(90, 90, 235);
font-family: monospace;
text-align: center;
border-color: blue;
width: 90%; //fallback
width: 90vw;
height: 90vh;
    #desc_text{
        //font-size: 5vw;
        font-size: 5vh;
        font-family: Sunny;
        color: rgb(0, 174, 255);
    }
}
#image{
    width: 40vh;
}
</style>
