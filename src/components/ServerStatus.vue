<template>
  <div>
    <h1>Server Status</h1>
    <BarChart :chartdata="chartdata" :options="options" style="height: 100px" />
    <v-row class="mt-2">
      <v-col>
        <h4 class="font-weight-light">Country</h4>
        <h4>Indonesia</h4>
      </v-col>
      <v-col>
        <h4 class="font-weight-light">Domain</h4>
        <h4>webbsite.co</h4>
      </v-col>
      <v-col>
        <h4><v-icon color="secondary">mdi-chevron-up-circle</v-icon></h4>
        <h4>2.0 mbps</h4>
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import BarChart from "./BarChart.vue";

@Component({
  components: {
    BarChart,
  },
})
export default class ServerStatus extends Vue {
  chartdata = {
    labels: [0, 20, 40, 60, 80, 100, 120, 140, 160, 180, 200, 220, 240, 260],
    datasets: [
      {
        label: "",
        backgroundColor: "#f8854c",
        data: [30, 15, 45, 30, 50, 10, 10, 30, 15, 45, 30, 50, 10, 10],
      },
      {
        label: "",
        backgroundColor: "#4e7e95",
        data: [
          -50, -30, -45, -30, -40, -50, -10, -50, -30, -45, -30, -40, -50, -10,
        ],
      },
    ],
  };
  options = {
    responsive: true,
    maintainAspectRatio: false,
    scales: {
      xAxes: [
        {
          display: false,
          stacked: true,
          barThickness: 6,
        },
      ],
      yAxes: [
        {
          display: false,
          stacked: true,
        },
      ],
    },
    legend: {
      display: false,
    },
  };
}
</script>

<style scoped lang="scss"></style>
