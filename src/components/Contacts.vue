<template>
  <div>
    <div class="d-flex">
      <h1>Contacts</h1>
      <v-btn class="ml-auto" text color="primary">View</v-btn>
    </div>
    <v-row no-gutters class="mt-4">
      <v-col v-for="contact in contacts" :key="contact">
        <UserAvatar :src="contact" :size="50" />
      </v-col>
    </v-row>
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
export default class Contacts extends Vue {
  contacts = [
    "https://randomuser.me/api/portraits/men/35.jpg",
    "https://randomuser.me/api/portraits/women/26.jpg",
    "https://randomuser.me/api/portraits/men/25.jpg",
    "https://randomuser.me/api/portraits/women/65.jpg",
    "https://randomuser.me/api/portraits/men/5.jpg",
  ];
}
</script>

<style scoped lang="scss"></style>
