<template>
  <v-badge :content="content" :value="value" overlap>
    <v-icon> {{ icon }} </v-icon>
  </v-badge>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class Badge extends Vue {
  @Prop({ default: "0" }) readonly content!: string;
  @Prop({ required: true }) readonly icon!: string;

  get value(): boolean {
    return this.content != "0";
  }
}
</script>

<style scoped lang="scss"></style>
