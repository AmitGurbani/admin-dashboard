<template>
  <div>
    <h3 class="font-weight-bold">User Reviews</h3>
    <v-row>
      <v-col v-for="(review, i) in reviews" :key="i">
        <UserReviewCard
          :avatar="review.avatar"
          :name="review.name"
          :rating="review.rating"
          :content="review.content"
        />
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import UserReviewCard from "./UserReviewCard.vue";

@Component({
  components: { UserReviewCard },
})
export default class UserReviews extends Vue {
  reviews = [
    {
      avatar: "https://randomuser.me/api/portraits/women/57.jpg",
      name: "Christian Jornald",
      rating: 3,
      content:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      avatar: "https://randomuser.me/api/portraits/men/91.jpg",
      name: "Christian Jornald",
      rating: 4,
      content:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
    {
      avatar: "https://randomuser.me/api/portraits/women/73.jpg",
      name: "Christian Jornald",
      rating: 3,
      content:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse architecto nihil debitis doloribus quam, accusantium ut, eius, possimus saepe dolorum corporis doloremque unde facilis voluptas eveniet ipsum ab et eligendi!",
    },
  ];
}
</script>

<style scoped lang="scss"></style>
