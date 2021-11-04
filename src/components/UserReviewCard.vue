<template>
  <v-card class="rounded-lg text-center mt-6">
    <UserAvatar class="mt-n6" :src="avatar" />
    <v-card-title>
      <v-spacer></v-spacer>
      <span class="font-weight-bold">{{ name }}</span>
      <v-spacer></v-spacer>
    </v-card-title>
    <v-card-text>
      <v-rating :value="rating" background-color="#e2ebf2" readonly></v-rating>
      <div class="review-content">{{ content }}</div>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
import UserAvatar from "./UserAvatar.vue";

@Component({
  components: { UserAvatar },
})
export default class UserReviewCard extends Vue {
  @Prop({ required: true }) readonly avatar!: string;
  @Prop({ required: true }) readonly name!: string;
  @Prop({ required: true }) readonly rating!: string;
  @Prop({ required: true }) readonly content!: string;
}
</script>

<style scoped lang="scss">
.review-content {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  line-clamp: 3;
  -webkit-box-orient: vertical;
}
</style>
