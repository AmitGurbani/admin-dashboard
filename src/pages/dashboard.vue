<template>
  <div>
    <h2>Dashboard</h2>
    <draggable v-model="dashBoardComponents">
      <component v-for="comp in dashBoardComponents" :key="comp" :is="comp" />
    </draggable>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import draggable from "vuedraggable";
import Highlights from "./../components/Highlights.vue";
import Activity from "./../components/Activity.vue";
import UserReviews from "./../components/UserReviews.vue";

@Component({
  components: { draggable, Highlights, Activity, UserReviews },
})
export default class Dashboard extends Vue {
  dashBoardComponents = ["Highlights", "Activity", "UserReviews"];
}
</script>

<style scoped lang="scss">
div > *:not(:last-child) {
  margin-bottom: 15px;
}
</style>
