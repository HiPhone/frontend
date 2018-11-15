<template>
  <v-app>
    <v-toolbar app color="light-blue">
      <v-toolbar-title class="headline ">
        <span>Spring Security登录界面</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>

    <v-content>
      <LoginPage/>
    </v-content>
  </v-app>
</template>

<script>
import LoginPage from "./components/LoginPage";

export default {
  name: "App",
  components: {
    LoginPage
  },
  data() {
    return {
      //
    };
  }
};
</script>
