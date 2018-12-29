<template>
  <div>
    <Menu active-name="1" style="height: 91vh">
      <MenuItem :name="item.name" v-for="item in serviceData">
        {{item.title}}
      </MenuItem> 
    </Menu>
  </div>
</template>

<script>
import api from "../utils/api.js";
export default {
  data() {
    return {
      serviceData: []
    };
  },
  methods: {
    queryServiceNames: function() {
      this.serviceData = [];
      axios
        .get(api.service_name)
        .then(response => {
          for (let i = 0; i < response.data.length; i++) {
            let tmp = {};
            tmp.title = response.data[i];
            tmp.name = "" + i + 1;
            this.serviceData.push(tmp);
          }
        })
    }
  },
  mounted: function() {
    this.queryServiceNames();
  }
};
</script>

<style>
h1 {
  margin-top: 20%;
}
</style>


