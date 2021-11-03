<template>
  <v-app class="app">
    <NavigationDrawer mini-variant>
      <LeftNavigationContent class="pl-6" />
    </NavigationDrawer>
    <v-main>
      <Toolbar />
      <HelloWorld />
    </v-main>
    <NavigationDrawer right color="#e3eaf0">
      <RightNavigationContent class="px-8" />
    </NavigationDrawer>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import NavigationDrawer from "./components/NavigationDrawer.vue";
import Toolbar from "./components/Toolbar.vue";
import LeftNavigationContent from "./components/LeftNavigationContent.vue";
import RightNavigationContent from "./components/RightNavigationContent.vue";

@Component({
  components: {
    HelloWorld,
    LeftNavigationContent,
    NavigationDrawer,
    RightNavigationContent,
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
