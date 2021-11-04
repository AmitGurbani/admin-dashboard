<template>
  <div>
    <ServerStatus />
    <Contacts />
    <Messages />
    <RecentActivity />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import ServerStatus from "./ServerStatus.vue";
import Contacts from "./Contacts.vue";
import Messages from "./Messages.vue";
import RecentActivity from "./RecentActivity.vue";

@Component({
  components: {
    ServerStatus,
    Contacts,
    Messages,
    RecentActivity,
  },
})
export default class RightNavigationContent extends Vue {}
</script>

<style scoped lang="scss">
div > *:not(:last-child) {
  margin-bottom: 20px;
}
</style>
