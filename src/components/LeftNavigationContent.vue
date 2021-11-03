<template>
  <div>
    <v-list-item class="ml-n3">
      <v-list-item-avatar>
        <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
      </v-list-item-avatar>
    </v-list-item>

    <v-list class="mt-4">
      <v-list-item v-for="item in items" :key="item.title" link>
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class LeftNavigationContent extends Vue {
  items = [
    { title: "Home", icon: "mdi-home-outline" },
    { title: "Messages", icon: "mdi-email-outline" },
    { title: "Users", icon: "mdi-account-group-outline" },
    { title: "Revenue", icon: "mdi-currency-usd" },
    { title: "Files", icon: "mdi-file-cabinet" },
    { title: "Documents", icon: "mdi-file-document-outline" },
    { title: "Wallet", icon: "mdi-wallet-outline" },
    { title: "Credit Cards", icon: "mdi-credit-card-outline" },
    { title: "Templates", icon: "mdi-folder-table-outline" },
    { title: "Profile", icon: "mdi-account-outline" },
    { title: "Calendar", icon: "mdi-calendar-blank-outline" },
    { title: "To Do", icon: "mdi-format-list-checks" },
  ];
}
</script>

<style scoped lang="scss"></style>
