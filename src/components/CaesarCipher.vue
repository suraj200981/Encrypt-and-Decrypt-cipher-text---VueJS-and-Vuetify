<template>
  <v-container>
    <v-row>
      <v-textarea
        outlined
        name="input-7-4"
        label="Plain text"
        v-model="plainText"
      ></v-textarea>
      <v-col class="d-flex" cols="12" sm="6">
        <v-btn @click="encryptCipher()">Encrypt</v-btn>
      </v-col>
    </v-row>
    <br />
    <br />
    <v-textarea
      background-color="amber lighten-4"
      color="orange orange-darken-4"
      :value="newString"
    ></v-textarea>
  </v-container>
</template>
<style scoped>
</style>
<script>
export default {
  name: "CaesarCipher",

  data: () => ({
    plainText: "",
    newString: "",
    encryptKey: 3,
  }),

  methods: {
    encryptCipher() {
  
  // Make an output variable
  var output = "";

  // Go through each character
  for (var i = 0; i < this.plainText.length; i++) {
    // Get the character we'll be appending
    var c = this.plainText[i];

    // check letter with regular expression
    if (c.match(/[a-z]/i)) {
      // Get its char code ascii
      var code = this.plainText.charCodeAt(i);

      // Uppercase letters
      if (code >= 65 && code <= 90) {
        c = String.fromCharCode(((code - 65 + this.encryptKey) % 26) + 65);
      }

      // Lowercase letters
      else if (code >= 97 && code <= 122) {
        c = String.fromCharCode(((code - 97 + this.encryptKey) % 26) + 97);
      }
    }

    // Append
    output += c;
  }

  // All done!
  this.newString= output;
    },
  },
};
</script>
