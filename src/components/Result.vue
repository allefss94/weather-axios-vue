<template>
  <section class="result">
    <h1>{{weather.name}} - {{weather.sys.country}}</h1>
    <img src="../assets/sunny.svg" alt="sunny" />
    <div class="temp1">
      <div class="temp">
        <p>Temperatura</p>
        <span>{{weather.main.temp.toFixed(0)}}º</span>
      </div>
      <div class="temp">
        <p>Sensação Térmica</p>
        <span>{{weather.main.feels_like.toFixed(0)}}º</span>
      </div>
    </div>
    <div class="temp1">
      <div class="temp">
        <p>Miníma</p>
        <span>
          <img src="../assets/minima.svg" alt />
          {{weather.main.temp_min.toFixed(0)}}º
        </span>
      </div>
      <div class="temp">
        <p>Máxima</p>
        <span>
          <img src="../assets/maxima.svg" alt />
          {{weather.main.temp_max.toFixed(0)}}º
        </span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ["weather"],
};
</script>

<style src="./style.css" scoped>
</style>