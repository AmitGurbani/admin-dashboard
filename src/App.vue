<template>
  <v-app>
    <NavigationDrawer />
    <v-main>
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import NavigationDrawer from "./components/NavigationDrawer.vue";

@Component({
  components: {
    HelloWorld,
    NavigationDrawer,
  },
})
export default class App extends Vue {}
</script>
