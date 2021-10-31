<template>
  <div class="home">
    <div v-if="typeof post != 'undefined'">
      <div v-if="post.wx_code === 60 || 61 ||  62 || 63 || 64 || 65 || 66 || 67">
      <rain :description="post.wx_desc" :temperature="post.temp_c" :windspeed="post.windspd_kmh"/>
   </div>
    <img alt="Vue logo" src="../assets/logo.png" />
    <div v-if="post.wx_code === 1">
      <p>{{post.wx_desc}}</p>
      <p>hello??</p>
      <cloudy :description="post.wx_desc" />
   </div>
    <img src="../assets/logo.png" />
      <p> The weather at Central Saint Martins is: {{post.wx_desc}} </p>
      <p> {{post.wx_code}} </p>
      <p>{{ post.temp_c }} Degrees C</p>
      <p>{{ post.windspd_kmh }} Km/h</p>
    </div>
  </div>
</template>

<script>
import rain from "@/components/rain.vue"
import cloudy from "@/components/cloudy.vue";
export default {
  components: {
    cloudy, rain
  },
  data() {
    return {
      app_id: 'b7e8cc96',
      api_key:'05126f4f85ac5bf5bdfedbcc6fa999d6',
      csm_url: 'http://api.weatherunlocked.com/api/current/51.536479,-0.124296',
      post: {},
    };
  },

  methods: {
    async getData() {
      try {
        console.log("getting data:");// print to console saying 'now i'll get data from api'
        const response = await fetch(`${this.csm_url}?app_id=${this.app_id}&app_key=${this.api_key}`);
        this.post = await response.json();
        
        console.log("now have the data: ",this.post); // now we have the data and it is: 
      } catch (error) {

        console.log(error); 
      }
    },
  },

  created() {
    this.getData(); // this.startRefreshingData() once - this calls set interval - pass set interval a function and an interview
    // 
    console.log(this.post);
  },
};
</script>
<style lang="scss" scoped>
#weather{
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3ac902;
  height: 100vh;
  background-color: #3ac902;
  
}
a{
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}
</style>