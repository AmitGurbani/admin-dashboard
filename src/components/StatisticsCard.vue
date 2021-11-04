<template>
  <v-card class="rounded-lg">
    <v-card-title class="font-weight-bold">Statistics</v-card-title>
    <v-card-text>
      <v-row>
        <v-col cols="9">
          <LineChart
            :chartdata="chartdata"
            :options="chartOptions"
            style="height: 125px"
          />
        </v-col>
        <v-col cols="3">
          <div class="vertical-center">
            <h5>This week</h5>
            <h1 class="primary--text">+32%</h1>

            <h5 class="mt-8">Last week</h5>
            <h1 class="secondary--text">24%</h1>
          </div>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import LineChart from "./LineChart.vue";

@Component({
  components: { LineChart },
})
export default class Statistics extends Vue {
  chartdata = {
    labels: [0, 20, 40, 60, 80, 100, 120],
    datasets: [
      {
        label: "",
        borderColor: "#f8854c",
        data: [10, 30, 25, 60, 90, 80, 10],
      },
      {
        label: "",
        borderColor: "#4e7e95",
        data: [80, 40, 75, 25, 90, 5, 100],
      },
    ],
  };
  chartOptions = {
    responsive: true,
    maintainAspectRatio: false,
    legend: {
      display: false,
    },
    scales: {
      yAxes: [
        {
          ticks: {
            beginAtZero: true,
          },
          gridLines: {
            display: false,
          },
        },
      ],
    },
    elements: {
      line: {
        fill: false,
        tension: 0,
        borderWidth: 4,
      },
      point: {
        radius: 0,
        hitRadius: 5,
        hoverRadius: 5,
      },
    },
  };
}
</script>

<style scoped lang="scss"></style>
