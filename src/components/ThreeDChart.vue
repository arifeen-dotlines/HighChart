<template>
    <section class="charts">
      <h3>3D Column Chart</h3>
      <vue-highcharts
        :options="options"
        :highcharts="Highcharts"
      ></vue-highcharts>
    </section>
  </template>
  <script>
  import VueHighcharts from "vue2-highcharts";
  import Highcharts3D from "highcharts/highcharts-3d";
  import Highcharts from "highcharts";
  
  Highcharts3D(Highcharts);
  
  const data = {
    chart: {
      renderTo: "container",
      type: "column",
      options3d: {
        enabled: true,
        alpha: 15,
        beta: 15,
        depth: 50,
        viewDistance: 25
      }
    },
    title: {
      text: "Chart rotation demo"
    },
    subtitle: {
      text: "Test options by dragging the sliders below"
    },
    plotOptions: {
      column: {
        depth: 25
      }
    },
    series: [
      {
        data: [
          29.9,
          71.5,
          106.4,
          129.2,
          144.0,
          176.0,
          135.6,
          148.5,
          216.4,
          194.1,
          95.6,
          54.4
        ]
      }
    ]
  };
  export default {
    components: {
      VueHighcharts
    },
    data() {
      return {
        options: data,
        Highcharts
      };
    }
  };
  </script>
  