<template>
  <div>
    <Row type="flex" justify="center">
      <h1>{{message}}</h1>
    </Row>
  </div>
</template>

<script>
import api from "../utils/api.js";
export default {
  data() {
    return {
      message: ""
    };
  },
  methods: {
    queryWelcomeMessage: function() {
      axios
        .get(api.user)
        .then(response => {
          this.message = response.data;
        })
        .catch(error => {});
    }
  },
  mounted: function() {
    this.queryWelcomeMessage();
  }
};
</script>

<style>
h1 {
  margin-top: 20%;
}
</style>


