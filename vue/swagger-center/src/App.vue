<template>
  <div id="app" >
    <Layout>
      <Header><p>Spring Security</p></Header>
      <Content><router-view></router-view></Content>
      <Footer>Copy Right HiPhone 2018</Footer>
    </Layout>
  </div>
</template>

<script>
export default {
  name: "app",
  components: {}
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
p {
  font-size: 30px;
  color: white;
}
</style>
