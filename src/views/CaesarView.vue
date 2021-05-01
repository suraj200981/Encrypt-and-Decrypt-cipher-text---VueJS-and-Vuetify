<template>
  <div class="home">
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <v-container fill-height fluid>
  <v-row align="center"
      justify="center">
    <CaesarCipher />
  </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
import CaesarCipher from "@/components/CaesarCipher.vue";

export default {
  name: "Home",
  components: {
    CaesarCipher,
  },
};
</script>
