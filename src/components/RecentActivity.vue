<template>
  <div>
    <h1>Recent Activity</h1>
    <v-list three-line>
      <v-list-item v-for="(activity, i) in activities" :key="i" class="pl-0">
        <v-list-item-avatar class="mx-n2 mt-2">
          <v-icon :color="activity.color"> mdi-circle </v-icon>
        </v-list-item-avatar>

        <v-list-item-content class="pl-3">
          <v-list-item-title>
            <div class="d-flex">
              <span class="font-weight-bold">{{ activity.title }}</span>
              <span class="ml-auto subtitle-2 font-weight-regular">{{
                activity.duration
              }}</span>
            </div>
          </v-list-item-title>
          <v-list-item-subtitle>{{ activity.subtitle }}</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class RecentActivity extends Vue {
  activities = [
    {
      color: "#ec8961",
      title: "Transaction Assets",
      duration: "2 Hours Ago",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      color: "#50bdc9",
      title: "New Email Register",
      duration: "3 Hours Ago",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      color: "#7f73d2",
      title: "Transaction Assets",
      duration: "3 Hours Ago",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      color: "#ebb6d7f",
      title: "New Email Register",
      duration: "2 Hours Ago",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
  ];
}
</script>

<style scoped lang="scss"></style>
