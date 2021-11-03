<template>
  <v-toolbar dense color="elevation-0" class="app pt-8">
    <Search />

    <v-spacer></v-spacer>

    <v-btn icon v-for="(item, i) in badgeItems" :key="i">
      <Badge :icon="item.icon" :content="item.content" />
    </v-btn>

    <UserAvatar src="https://randomuser.me/api/portraits/men/85.jpg" />
    <v-list-item two-line style="flex: none">
      <v-list-item-content>
        <v-list-item-title>Madison Eve</v-list-item-title>
        <v-list-item-subtitle>Admin</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
  </v-toolbar>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import Badge from "./Badge.vue";
import Search from "./Search.vue";
import UserAvatar from "./UserAvatar.vue";

@Component({
  components: {
    Badge,
    Search,
    UserAvatar,
  },
})
export default class Toolbar extends Vue {
  badgeItems = [
    {
      icon: "mdi-message-text-outline",
      content: "2",
    },
    {
      icon: "mdi-bullhorn-outline",
      content: "2",
    },
    {
      icon: "mdi-cog-outline",
      content: "0",
    },
  ];
}
</script>

<style scoped lang="scss"></style>
