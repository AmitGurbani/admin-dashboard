<template>
  <v-text-field
    flat
    solo
    :label="label"
    :prepend-inner-icon="icon"
    :style="style"
    hide-details
  ></v-text-field>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class Search extends Vue {
  @Prop({ default: "Search here..." }) readonly label!: string;
  @Prop({ default: "mdi-magnify" }) readonly icon!: string;
  @Prop({ default: "300px" }) readonly width!: string;

  get style(): string {
    return `max-width: ${this.width}`;
  }
}
</script>

<style scoped lang="scss"></style>
