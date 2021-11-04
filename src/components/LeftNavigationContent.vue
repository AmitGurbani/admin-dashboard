<template>
  <div>
    <v-list-item>
      <UserAvatar src="https://randomuser.me/api/portraits/men/34.jpg" />
    </v-list-item>

    <v-list class="mt-2">
      <v-list-item v-for="item in items" :key="item.title" link>
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-icon
              v-bind="attrs"
              v-on="on"
              :color="item.selected ? 'primary' : ''"
              >{{ item.icon }}</v-icon
            >
          </template>
          <span>{{ item.title }}</span>
        </v-tooltip>
      </v-list-item>
      <v-list-item link @click="$emit('logout')">
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-icon v-bind="attrs" v-on="on">mdi-logout-variant</v-icon>
          </template>
          <span>Logout</span>
        </v-tooltip>
      </v-list-item>
    </v-list>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import UserAvatar from "./UserAvatar.vue";

@Component({
  components: {
    UserAvatar,
  },
})
export default class LeftNavigationContent extends Vue {
  items = [
    { title: "Home", icon: "mdi-home-outline", selected: true },
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
