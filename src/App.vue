<template>
  <v-app class="app">
    <NavigationDrawer mini-variant>
      <LeftNavigationContent />
    </NavigationDrawer>
    <v-main>
      <Toolbar />
      <v-container>
        <Dashboard />
      </v-container>
    </v-main>
    <NavigationDrawer right color="#e3eaf0">
      <RightNavigationContent class="px-3" />
    </NavigationDrawer>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import Dashboard from "./pages/dashboard.vue";
import NavigationDrawer from "./components/NavigationDrawer.vue";
import Toolbar from "./components/Toolbar.vue";
import LeftNavigationContent from "./components/LeftNavigationContent.vue";
import RightNavigationContent from "./components/RightNavigationContent.vue";

@Component({
  components: {
    Dashboard,
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

::-webkit-scrollbar {
  display: none;
}

.vertical-center {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
</style>
