<template>
 <div id='vanilla'>
   <h1>The weather at Central Saint Martins is: {{description}}</h1>
   <h1>The Temperature is: {{temperature}} °C</h1>
   <h1>The Windspeed is: {{windspeed}} km/h</h1>
 </div>
</template>
 
<script>
export default {
// data taken from Api Call in App.vue
 props: ['description','temperature', 'windspeed']
}
</script>
<style lang="scss"  scoped>
#vanilla{
font-family: monospace;
text-align: center;
border-color: blue;
width: 90%; //fallback
width: 90vw;
height: 90vh;
}
#image{
    width: 40vh;
}
</style>
