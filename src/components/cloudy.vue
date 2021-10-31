<template>
 <div id='cloudy'>
   <h1>The weather at Central Saint Martins is: {{description}}</h1>
   <h1>The Temperature is: {{temperature}} °C</h1>
   <h1>The Windspeed is: {{windspeed}} km/h</h1>
   <img id="image" src="../assets/cloudy/1.png" />
 </div>
</template>
 
<script>
export default {
 props: ['description','temperature', 'windspeed']
}
</script>
<style lang="scss"  scoped>
#cloudy{
//background-color: rgb(90, 90, 235);
font-family: monospace;
text-align: left;
border-color: blue;
width: 90%; //fallback
width: 90vw;
height: 70vh;
    h1{
        //font-size: 5vw;
        font-size: 5vh;
        font-family: cursive;
        color: rgb(62, 62, 62);
    }
}
#image{
    width: 50vw;
}
</style>
