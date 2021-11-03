<template>
  <v-app class="app">
    <NavigationDrawer />
    <v-main>
      <Toolbar />
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import NavigationDrawer from "./components/NavigationDrawer.vue";
import Toolbar from "./components/Toolbar.vue";

@Component({
  components: {
    HelloWorld,
    NavigationDrawer,
    Toolbar,
  },
})
export default class App extends Vue {}
</script>
<style lang="scss">
.app {
  background-color: #f1f6fa !important;
}
</style>
