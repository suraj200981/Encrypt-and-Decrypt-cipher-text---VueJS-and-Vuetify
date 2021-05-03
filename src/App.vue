<template>
  <v-app>
    <v-card class="overflow-hidden">
      <v-app-bar absolute color="#6A76AB" dark prominent>
        <template v-slot:img="{ props }">
          <v-img
            v-bind="props"
            gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
          ></v-img>
        </template>
        <v-toolbar-title>Cipher Encryption Decryption App</v-toolbar-title>

        <v-spacer></v-spacer>

        <template v-slot:extension>
          <v-tabs align-with-title>
            <v-tab to="/">Caesar</v-tab>
            <v-tab to="/about">Vigenere</v-tab>
            <v-tab>Transposition</v-tab>
          </v-tabs>
        </template>
      </v-app-bar>
      <v-sheet>
        <v-container style="height: 176px"></v-container>
      </v-sheet>
    </v-card>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <router-view></router-view>
      </v-container>
    </v-main>

    <v-footer dark padless>
      <v-card flat tile class="indigo lighten-1 white--text text-center">
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text pt-0" style="width=100px">
          This app is still being developed and is not yet completed. Please
          feel free to make changes where possible. This app is still being
          developed and is not yet completed. Please feel free to make changes
          where possible.This app is still being developed and is not yet
          completed. Please feel free to make changes where possible. This app
          is still being developed and is not yet completed. Please feel free to
          make changes where possible.
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Suraj Sharma</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>
<script>
export default {
  name: "App",
  data: () => ({
    icons: ["mdi-github", "mdi-linkedin"],
  }),
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
