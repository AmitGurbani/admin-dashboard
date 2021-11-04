<template>
  <div>
    <div class="d-flex">
      <h1>Messages</h1>
      <v-btn class="ml-auto" text color="primary">View</v-btn>
    </div>
    <v-list two-line>
      <v-list-item v-for="(message, i) in messages" :key="i" class="pl-0">
        <UserAvatar :src="message.avatar" :size="50" />

        <v-list-item-content class="pl-3">
          <v-list-item-title class="font-weight-bold">{{
            message.title
          }}</v-list-item-title>
          <v-list-item-subtitle>{{ message.subtitle }}</v-list-item-subtitle>
        </v-list-item-content>
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
export default class Messages extends Vue {
  messages = [
    {
      avatar: "https://randomuser.me/api/portraits/women/19.jpg",
      title: "Samantha William",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      avatar: "https://randomuser.me/api/portraits/men/17.jpg",
      title: "Tony Soap",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      avatar: "https://randomuser.me/api/portraits/men/27.jpg",
      title: "Jordan Nico",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      avatar: "https://randomuser.me/api/portraits/women/45.jpg",
      title: "Nadila Adja",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
  ];
}
</script>

<style scoped lang="scss"></style>
