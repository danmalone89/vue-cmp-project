<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <app-server v-for="server in servers" :server="server"></app-server>
    </ul>
  </div>
</template>

<script>
import Server from "./Server.vue";
export default {
  data() {
    return {
      servers: [
        { id: 1, status: "Normal" },
        { id: 2, status: "Unknwon" },
        { id: 3, status: "Normal" },
        { id: 4, status: "Critical" }
      ]
    };
  },
  components: {
    appServer: Server
  }
};
</script>

<style>
</style>
