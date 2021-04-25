<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <CaesarCipher />
  </div>
</template>

<script>
// @ is an alias to /src
import CaesarCipher from '@/components/CaesarCipher.vue'

export default {
  name: 'Home',
  components: {
    CaesarCipher
  }
}
</script>
