<template>
  <div id="app">
    <section class="search">
      <h2>COMO ESTA O CLIMA HOJE?</h2>
      <input type="text" placeholder="Parauapebas" v-model="city" @keydown.enter="getWeather(city)" />
      <button type="button" @click="getWeather(city)">BUSCAR</button>
    </section>
    <transition name="fade" mode="out-in" appear>
      <Result :weather="weather" />
    </transition>
  </div>
</template>

<script>
import Result from "@/components/Result.vue";
export default {
  components: { Result },
  data() {
    return {
      weather: {},
      city: "",
    };
  },

  methods: {
    getWeather(city = "parauapebas") {
      this.$http
        .get(
          `https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=dfe656cb2848b53caf551a02003f0f3b`
        )
        .then((response) => {
          this.weather = response.data;
          this.city = "";
        });
    },
  },
  mounted() {
    this.getWeather();
  },
};
</script>

<style src="./style.css" scoped>
</style>


