<template>
  <div class="app, centered">
    <div v-if="typeof post != 'undefined'">
      <div v-if="post.wx_code === 60 || post.wx_code === 61 ||  post.wx_code === 62 || post.wx_code ===63 || post.wx_code === 64 || post.wx_code === 65 || post.wx_code === 66 || post.wx_code === 67|| post.wx_code === 21">
        <rain :description="post.wx_desc" :temperature="post.temp_c" :windspeed="post.windspd_kmh"/>
      </div>
      <div v-if="post.wx_code === 0">
        <sunny :description="post.wx_desc" :temperature="post.temp_c" :windspeed="post.windspd_kmh"/>
      </div>
      <div v-if="post.wx_code === 1 ">
        <sunny_cloudy :description="post.wx_desc" :temperature="post.temp_c" :windspeed="post.windspd_kmh"/>
      </div>
      <div v-if="post.wx_code === 2 || post.wx_code === 3">
        <cloudy :description="post.wx_desc" :temperature="post.temp_c" :windspeed="post.windspd_kmh"/>
      </div>
    </div>
  </div>
</template>
<script>
import rain from "@/components/rain.vue"
import cloudy from "@/components/cloudy.vue";
import sunny from "@/components/sunny.vue";
import sunny_cloudy from "@/components/sunny_cloudy.vue";
export default {
  components: {
    cloudy, rain, sunny, sunny_cloudy
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
    startRefreshingData() {
        this.getData();
        setInterval(() => this.getData(), 30000);
    },
    async getData() {
      try {
        console.log("Getting data");// print to console saying 'now i'll get data from api'
        const response = await fetch(`${this.csm_url}?app_id=${this.app_id}&app_key=${this.api_key}`);
        this.post = await response.json();
        
        console.log("Now have the data: ",this.post); // now we have the data and it is: 
      } catch (error) {

        console.log(error); 
      }
    },

  },

  created() {
    //this.getData(); // this.startRefreshingData() once - this calls set interval - pass set interval a function and an interview
    this.startRefreshingData(); 
    console.log(this.post);
  },
};
</script>
<style lang="scss">
@font-face {
  font-family: "Cloudy";
  src: url(./fonts/Cloudy/Alphasmoke-OOX6.ttf) format("truetype");
}
@font-face{
  font-family: "Sunny";
  src: url(./fonts/Sunny/101KidletSunshineBet-0OmG.ttf) format("truetype");
}
@font-face {
  font-family: "Rainy";
  src: url(./fonts/Rainy/LcrRainyDaze-P3zg.ttf) format("truetype");
}
.centered {
  height: 10em;
    position: fixed;
  top: 25%;
  left: 50%;
  /* bring your own prefixes */
  transform: translate(-50%, -50%);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
  text-align: right;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
