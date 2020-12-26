<template>
  <div id="app" class="container">
   <div class="row mt-5" v-if="arrPositive.length > 0" >
     <div class="col">
       <h2>Positive</h2>
       <line-chart :chartData="arrPositive" :options="chartOptions" label="Positive"></line-chart>
     </div>

   </div>
  </div>
</template>

<script>
import axios from 'axios';
import moment from 'moment';
import LineChart from './components/LineChart'

export default {
  name: 'app',
  components: {
    LineChart
    
  },
  data(){
    return {
      arrPositive: [],
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false
      }
  
    };
  },
    created()  {
    axios.get("https://covidtracking.com/api/us/daily").then(response => {
      const data = response.data;

      data.forEach(singleData => {
        const date = moment(singleData.date,"YYYYMMDD").format("MM/DD");

        const { positive } = singleData;

        this.arrPositive.push({date, total: positive});

      });
    });

  }
}
</script>

<style>

</style>
