<template>
  <div>
    <h2>Dashboard</h2>
    <Highlights />
    <Activity />
    <UserReviews />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import Highlights from "./../components/Highlights.vue";
import Activity from "./../components/Activity.vue";
import UserReviews from "./../components/UserReviews.vue";

@Component({
  components: { Highlights, Activity, UserReviews },
})
export default class Dashboard extends Vue {}
</script>

<style scoped lang="scss">
div > *:not(:last-child) {
  margin-bottom: 15px;
}
</style>
