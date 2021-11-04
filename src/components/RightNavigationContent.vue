<template>
  <div>
    <draggable v-model="componentOptions">
      <component v-for="comp in componentOptions" :key="comp" :is="comp" />
    </draggable>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import draggable from "vuedraggable";
import ServerStatus from "./ServerStatus.vue";
import Contacts from "./Contacts.vue";
import Messages from "./Messages.vue";
import RecentActivity from "./RecentActivity.vue";

@Component({
  components: {
    draggable,
    ServerStatus,
    Contacts,
    Messages,
    RecentActivity,
  },
})
export default class RightNavigationContent extends Vue {
  componentOptions = ["ServerStatus", "Contacts", "Messages", "RecentActivity"];
}
</script>

<style scoped lang="scss">
div > *:not(:last-child) {
  margin-bottom: 20px;
}
</style>
