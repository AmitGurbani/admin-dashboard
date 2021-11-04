<template>
  <v-card class="rounded-lg">
    <v-card-title class="font-weight-bold">User Profile</v-card-title>
    <v-card-text>
      <v-row>
        <v-col cols="6">
          <DoughnutChart
            :chartdata="chartdata"
            :options="chartOptions"
            style="height: 125px"
          />
        </v-col>
        <v-col cols="6">
          <div class="vertical-center mt-8">
            <h1>75%</h1>
            <div class="d-flex my-3" v-for="(task, i) in tasks" :key="i">
              <v-icon small :color="task.color"> mdi-circle </v-icon>
              <span class="mx-2">{{ task.label }}</span>
              <span class="ml-auto">{{ task.status }}</span>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import DoughnutChart from "./DoughnutChart.vue";

@Component({
  components: { DoughnutChart },
})
export default class UserProfileActivityCard extends Vue {
  tasks = [
    {
      label: "Complete",
      status: "50%",
      color: "primary",
    },
    {
      label: "In Progress",
      status: "45%",
      color: "secondary",
    },
  ];
  chartdata = {
    labels: [],
    datasets: [
      {
        label: "",
        backgroundColor: ["#4e7e95", "#e2ebf2", "#f8854c"],
        data: [38, 40, 75],
      },
    ],
  };
  chartOptions = {
    responsive: true,
    maintainAspectRatio: false,
    cutoutPercentage: 80,
  };
}
</script>

<style scoped lang="scss"></style>
