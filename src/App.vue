<template>
  <v-app class="app">
    <template v-if="!loginDialog">
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
    </template>
    <v-dialog v-model="loginDialog" persistent max-width="600px">
      <v-card>
        <v-card-title>Login</v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  hide-details
                  prepend-icon="mdi-email"
                  label="Email"
                  v-model="email"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  hide-details
                  prepend-icon="mdi-eye"
                  label="Password"
                  v-model="password"
                  type="password"
                  required
                ></v-text-field>
              </v-col>
              <v-col class="text-center">
                <div class="error--text" v-if="invalidCredentials">
                  Invalid email or password
                </div>
                <v-btn color="primary" @click="verifyUser()">Submit</v-btn>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
      </v-card>
    </v-dialog>
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
export default class App extends Vue {
  loginDialog = true;
  email = "";
  password = "";
  invalidCredentials = false;

  verifyUser() {
    if (
      this.email === "admin@cloudworx.com" &&
      this.password === "mysecurepassword"
    ) {
      this.loginDialog = false;
    } else {
      this.invalidCredentials = true;
    }
  }
}
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
