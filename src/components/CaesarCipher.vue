<template>
  <center>
    <v-container>
      <v-row>
        <v-textarea
          outlined
          name="input-7-4"
          label="Plain text"
          v-model="plainText"
          style="width: 1000px"
        ></v-textarea>
        <v-col class="d-flex" cols="12" sm="6">
          <v-btn @click="encryptCipher()">Encrypt</v-btn>
        </v-col>
      </v-row>
      <br />
      <br />
      <v-row>
        <v-textarea
          background-color="amber lighten-4"
          color="orange orange-darken-4"
          label="Cipher text"
          v-model="newStringEncrypted"
          style="width: 1000px"
        ></v-textarea>
        <v-col class="d-flex" cols="12" sm="6">
          <v-btn @click="decryptCipher()">Decrypt</v-btn>
        </v-col>
      </v-row>
    </v-container>
  </center>
</template>
<style scoped>
</style>
<script>
export default {
  name: "CaesarCipher",

  data: () => ({
    plainText: "",
    cipherText: "",
    newStringEncrypted: "",
    newStringDecrypted: "",
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
      this.newStringEncrypted = output;
      console.log(this.newString);
    },
    decryptCipher() {
      var decryptKey = this.encryptKey;
      decryptKey = -Math.abs(decryptKey);
      // Make an output variable
      var output = "";
      // Go through each character
      for (var i = 0; i < this.newStringEncrypted.length; i++) {
        // Get each char
        var c = this.newStringEncrypted[i];
        // check letter with regular expression
        if (c.match(/[a-z]/i)) {
          // Get its char code ascii at each letter
          var code = this.newStringEncrypted.charCodeAt(i);
          // shifting the values with an uppercase letters. Value cant be higher then Z.
          // reversing the shift inital shift val by adding 26 before the wrap around
          if (code <= 90) {
            c = String.fromCharCode(((code - 65 + decryptKey + 26) % 26) + 65); //the + A coverts the int value back to alphabet value.
          }
          // shifting the values with an uppercase letters. Value cant be higher then z.
          // reversing the shift inital shift val by adding 26 before the wrap around
          else if (code <= 122) {
            c = String.fromCharCode(((code - 97 + decryptKey + 26) % 26) + 97); //the + a coverts the int value back to alphabet value.
          }
        }
        // Append
        output += c;
        console.log(output);
      }
      // All done!
      this.plainText = output;
      console.log(this.plainText);
    },
  },
};
</script>
