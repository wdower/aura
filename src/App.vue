<template>
  <v-app class="google-font">
    <v-content>
      <!-- <v-snackbar
        v-model="snackWithButtons"
        :timeout="timeout"
        bottom
        left
        class="snack"
      >
        {{ snackWithBtnText }}
        <v-spacer />
        <v-btn dark text color="#00f500" @click.native="refreshApp">{{
          snackBtnText
        }}</v-btn>
        <v-btn icon @click="snackWithButtons = false">
          <v-icon>mdi-close</v-icon>
        </v-btn>
      </v-snackbar> -->

      <AdminToolbar v-if="$route.meta.requiresAuth" />
      <AuraToolbar v-if="!$route.meta.requiresAuth" />

      <AdminDrawer v-if="$route.meta.requiresAuth" />
      <AuraDrawer v-if="!$route.meta.requiresAuth" />

      <AuraView class />

      <AuraFooter v-if="!$route.meta.requiresAuth" />
    </v-content>

    <!-- <AuraBottomNav v-if="!$route.meta.requiresAuth" class="d-flex d-sm-none" /> -->
  </v-app>
</template>

<script>
  import AdminToolbar from "./components/Admin/Core/AdminToolbar";
  import AdminDrawer from "./components/Admin/Core/AdminDrawer";

  import AuraToolbar from "./components/core/Toolbar";
  import AuraDrawer from "./components/core/Drawer";
  // import AuraBottomNav from "./components/core/BottomNav";
  import AuraView from "./components/core/View";
  import AuraFooter from "./components/core/Footer";

  export default {
    name: "App",
    components: {
      AdminDrawer,
      AdminToolbar,
      AuraToolbar,
      AuraDrawer,
      AuraView,
      // AuraBottomNav,
      AuraFooter,
    },
    data: () => ({
      refreshing: false,
      registration: null,
      snackBtnText: "",
      snackWithBtnText: "",
      snackWithButtons: false,
      timeout: 7000,
    }),
    created() {
      // Listen for swUpdated event and display refresh snackbar as required.
      document.addEventListener("swUpdated", this.refreshApp, {once: true});
      console.log("eventListener added");
      // Refresh all open app tabs when a new service worker is installed.
      navigator.serviceWorker.addEventListener("controllerchange", () => {
        console.log("controller change added");
        if (this.refreshing) return;
        this.refreshing = true;
        window.location.reload();
      });
    },
    methods: {
      // showRefreshUI(e) {
      //   console.log("showRefresh called");
      //   this.registration = e.detail;
      //   this.snackBtnText = "Refresh";
      //   this.snackWithBtnText = "New version available!";
      //   this.snackWithButtons = true;
      // },
      refreshApp() {
        //console.log("refreshApp called");
        // this.snackWithButtons = false;
        if (!this.registration || !this.registration.waiting) {
          return;
        }
        this.registration.waiting.postMessage("skipWaiting");
      },
    },
  };
</script>

<style scoped>
  /* Provide better right-edge spacing when using an icon button there. */
  .snack >>> .v-snack__content {
    padding-right: 16px;
  }
</style>
