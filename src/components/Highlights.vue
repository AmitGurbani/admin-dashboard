<template>
  <v-row>
    <v-col v-for="(highlight, i) in highlights" :key="i">
      <HighlightCard
        :icon="highlight.icon"
        :title="highlight.title"
        :count="highlight.count"
        :color="highlight.color"
      />
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import HighlightCard from "./HighlightCard.vue";

@Component({
  components: { HighlightCard },
})
export default class Highlights extends Vue {
  highlights = [
    {
      icon: "mdi-briefcase-outline",
      title: "Projects",
      count: 932,
      color: "primary",
    },
    {
      icon: "mdi-note-multiple-outline",
      title: "Side Projects",
      count: 932,
      color: "#4ebeda",
    },
    {
      icon: "mdi-chart-timeline-variant",
      title: "Investment",
      count: 932,
      color: "#8373d4",
    },
    {
      icon: "mdi-gold",
      title: "Assets",
      count: 932,
      color: "#da6f7c",
    },
  ];
}
</script>

<style scoped lang="scss"></style>
