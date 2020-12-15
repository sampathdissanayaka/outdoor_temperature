<template>
  <div id="app">
    <h2>Outdoor Temperature</h2>
    <line-chart :data="chartData"></line-chart>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
       chartData: {
     
         "2018-12-01 10:20:12":"35C",
         "2018-12-02 10:20:12":"3C",
         "2018-12-03 10:20:12":"10C",
         "2018-12-04 10:20:12":"22C",
         "2018-12-05 10:20:12":"40C",
         "2018-12-06 10:20:12":"16C",
         "2018-12-07 10:20:12":"25C",
        

       }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}


</style>
