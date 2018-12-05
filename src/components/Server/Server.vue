<template>
  <a @click="serverSelected()" class="list-group-item">
    <i class="fas fa-server"></i>
    Server {{ server.id }}
  </a>
</template>

<script>
import { serverBus } from "../../main.js";

export default {
  props: ["server"], // this is received from 'id:="server.id" in Servers.vue
  methods: {
    serverSelected() {
      // here this.id refers to the id in our props
      serverBus.$emit("serverSelected", this.server);
    }
  }
};
</script>

<style>
</style>
