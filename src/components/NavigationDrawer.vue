<template>
  <v-navigation-drawer
    app
    :mini-variant="miniVariant"
    :right="right"
    permanent
    mini-variant-width="90"
    width="315"
    class="pt-4"
    :color="color"
  >
    <slot></slot>
  </v-navigation-drawer>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class NavigationDrawer extends Vue {
  @Prop({ default: false }) readonly miniVariant!: boolean;
  @Prop({ default: false }) readonly right!: boolean;
  @Prop({ default: "#ffffff" }) readonly color!: string;
}
</script>

<style scoped lang="scss"></style>
