<template>
  <div class="col-xs-12 col-sm-6">
    <p v-if="!server">Please select a server</p>
    <div v-else>
      <p>Server {{ server.id }} is {{ server.status }}</p>
      <hr>
      <button class="btn btn-sm btn-success" @click="setNormal()">Set Normal</button>
      <button class="btn btn-sm btn-danger" @click="setCritical()">Set Critical</button>
    </div>
  </div>
</template>

<script>
import { serverBus } from "../../main.js";
export default {
  data() {
    return {
      server: null
    };
  },
  created() {
    serverBus.$on("serverSelected", server => {
      this.server = server;
    });
  },
  methods: {
    setNormal() {
      this.server.status = "Normal";
    },
    setCritical() {
      this.server.status = "Critical";
    }
  }
};
</script>

<style>
</style>
