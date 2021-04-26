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
    <CaesarCipher />
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
