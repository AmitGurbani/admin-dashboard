<template>
  <v-card height="100" class="rounded-lg">
    <v-card-text class="vertical-center">
      <v-row>
        <v-col cols="4" class="text-center"
          ><v-icon :color="color" large>{{ icon }}</v-icon></v-col
        >
        <v-col>
          <h4>{{ title }}</h4>
          <h3>{{ count }}</h3>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component({
  components: {},
})
export default class HighlightCard extends Vue {
  @Prop({ required: true }) readonly icon!: string;
  @Prop({ required: true }) readonly title!: string;
  @Prop({ required: true }) readonly count!: string;
  @Prop({ required: true }) readonly color!: string;
}
</script>

<style scoped lang="scss"></style>
