<template>
  <a @click="serverSelected()" class="list-group-item">
    <i class="fas fa-server"></i>
    Server {{ server.id }}
  </a>
</template>

<script>
import { serverBus } from "../../main.js";

export default {
  props: ["server"], // this is received from 'server:="server" in Servers.vue
  methods: {
    serverSelected() {
      serverBus.$emit("serverSelected", this.server);
    }
  }
};
</script>

<style>
</style>
