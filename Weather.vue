<template>
  <div>
    <h1>Book Database</h1>
    
     <button v-on:click="getWeatherData">Books which you own: </button>
     
    <div v-for="weatherData in weatherDataList" :key="weatherData.id" class="weather-data">
        
      <div class="weather-stats">
        <div>
          <span>{{weatherData.title}}</span>
          
        </div>
       </div>
       </div>
  </div>
  
</template>

<script>
export default {
  name: 'Weather',
  data() {
    return {
      weatherDataList: [],
      booksData: []
    }
    },
  methods: {
    getWeatherData() {
      fetch("weather.json")
        .then(response => response.json())
        .then(data => (this.weatherDataList = data));
    },
    getBooksData(){
        fetch("books.json")
        .then(response =>response.json())
        .then(data =>(this.booksData=data));
  }
}
}
</script>

<style scoped>
.weather-data {
  display: flex;
  align-items: center;
  margin-top: 20px;
  margin-left: 20px;
  border-bottom: 2px solid #ccc;
  padding: 20px;
}

.weather-icon {
  flex-grow: 1;
}

.weather-stats {
  flex-grow: 8;
  text-align: left;
  padding-left: 20px;
}

.weather-stats .location {
  font-size: 30px;
}

.weather-temp {
  flex-grow: 1;
  font-size: 35px;
}

img {
  width: 70px;
}

button {
    padding:10px;
    background-color: #1aa832;
    color: white;
    border: 1px solid #ccc;
}
</style>