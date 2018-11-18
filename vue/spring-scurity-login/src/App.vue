<template>
  <div id="app" class="layout">
    <Layout>
      <Header><h1>Spring Security</h1></Header>
      <Content><LoginPage></LoginPage></Content>
      <Footer>Copy Right HiPhone 2018</Footer>
    </Layout>
  </div>
</template>

<script>
import LoginPage from './components/LoginPage.vue'
export default {
  name: 'app',
  components: {
    LoginPage
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h1 {
  color: white
}
</style>
