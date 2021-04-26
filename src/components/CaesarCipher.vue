<template>
  <v-container>
    <v-textarea
      outlined
      name="input-7-4"
      label="Plain text"
      value=""
      v-model="plainText"
    ></v-textarea>
    <br />
    <br />
    <v-textarea
      background-color="amber lighten-4"
      color="orange orange-darken-4"
      :value="plainText"
    ></v-textarea>
  </v-container>
</template>

<script>
export default {
  name: "CaesarCipher",

  data: () => ({
    plainText: ""
  }),
};
</script>
