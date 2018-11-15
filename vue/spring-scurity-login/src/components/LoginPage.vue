<template>
  <v-container fluid fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm8 md3>
        <v-card class="elevation-18">
          <v-toolbar dark color="light-blue">
            <v-toolbar-title ><b>用户登陆</b></v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form >
              <v-text-field prepend-icon="person" label="用户名：" type="text" v-model="loginMsg.username"></v-text-field>
              <v-text-field prepend-icon="lock"  label="密码" type="password" v-model="loginMsg.password"></v-text-field>
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-btn color="light-blue" style="width: 100%; color: white" @click="login"><b>登陆</b></v-btn>
          </v-card-actions>
          <br>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import api from "../utils/api.js";
import qs from "qs";
export default {
  data: () => ({
    loginMsg: {
      username: "",
      password: ""
    }
  }),
  methods: {
    login: function() {
      axios.post(api.login, qs.stringify(this.loginMsg), response => {
        if (response.data.returnCode === 0) {
          window.href.location = rsponse.data.data;
        } else {
        }
      });
    }
  }
};
</script>

<style>
</style>
