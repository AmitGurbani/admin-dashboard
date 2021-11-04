<template>
  <div>
    <h3 class="mb-3 font-weight-bold">Activity</h3>
    <v-row>
      <v-col cols="9">
        <BarChart
          :chartdata="barChartdata"
          :options="barChartOptions"
          style="height: 300px"
        />
      </v-col>
      <v-col cols="3">
        <v-row>
          <v-col cols="12">
            <h5 class="font-weight-light">Completed</h5>
            <h4 class="font-weight-bold">932 Task</h4>
            <LineChart
              :chartdata="lineCharts[0].chartData"
              :options="lineCharts[0].options"
              style="height: 75px"
            />
          </v-col>
          <v-col cols="12">
            <h5 class="font-weight-light">Total</h5>
            <h4 class="font-weight-bold">932 Task</h4>
            <LineChart
              :chartdata="lineCharts[1].chartData"
              :options="lineCharts[1].options"
              style="height: 75px"
            />
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="4">
        <UserProfileActivityCard />
      </v-col>
      <v-col cols="8">
        <StatisticsCard />
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import BarChart from "./BarChart.vue";
import LineChart from "./LineChart.vue";
import UserProfileActivityCard from "./UserProfileActivityCard.vue";
import StatisticsCard from "./StatisticsCard.vue";

const barChartLabels = [
  "Jan",
  "Fe",
  "Mar",
  "Apr",
  "Ma",
  "Jun",
  "Jul",
  "Au",
  "Sep",
  "Oct",
  "Nov",
  "Dec",
];

@Component({
  components: { BarChart, LineChart, UserProfileActivityCard, StatisticsCard },
})
export default class Activity extends Vue {
  barChartdata = {
    labels: barChartLabels,
    datasets: [
      {
        label: "",
        backgroundColor: barChartLabels.map((label) =>
          label == "Jul" ? "#f8854c" : "#4e7e95"
        ),
        data: [56, 35, 25, 35, 30, 45, 58, 40, 40, 50, 35, 80],
      },
    ],
  };
  barChartOptions = {
    responsive: true,
    maintainAspectRatio: false,
    scales: {
      xAxes: [
        {
          gridLines: {
            display: false,
          },
        },
      ],
    },
    legend: {
      display: false,
    },
  };

  lineCharts = [
    {
      options: {
        responsive: true,
        maintainAspectRatio: false,
        legend: {
          display: false,
        },
        scales: {
          xAxes: [
            {
              display: false,
            },
          ],
          yAxes: [
            {
              display: false,
            },
          ],
        },
        elements: {
          line: {
            fill: false,
            tension: 0,
            borderWidth: 2,
          },
          point: {
            radius: 0,
            hitRadius: 5,
            hoverRadius: 5,
          },
        },
      },
      chartData: {
        labels: [0, 20, 40, 60, 80, 100, 120],
        datasets: [
          {
            label: "",
            borderColor: "#f8854c",
            data: [90, 30, 95, 30, 105, 80, 10],
          },
        ],
      },
    },
    {
      options: {
        responsive: true,
        maintainAspectRatio: false,
        legend: {
          display: false,
        },
        scales: {
          xAxes: [
            {
              display: false,
            },
          ],
          yAxes: [
            {
              display: false,
            },
          ],
        },
        elements: {
          line: {
            fill: false,
            tension: 0,
            borderWidth: 2,
          },
          point: {
            radius: 0,
            hitRadius: 5,
            hoverRadius: 5,
          },
        },
      },
      chartData: {
        labels: [0, 20, 40, 60, 80, 100, 120],
        datasets: [
          {
            label: "",
            borderColor: "#4e7e95",
            data: [30, 90, 45, 30, 105, 10, 80],
          },
        ],
      },
    },
  ];
}
</script>

<style scoped lang="scss"></style>
