<template>
  <v-app>
    <v-app-bar app color="pink" dark>
      <v-toolbar-title class="headline text-uppercase">
        <router-link to="/" style="color:white;text-decoration:none;"><span>MUSIC SEARCH</span></router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        to="/"
      >
        HOME
      </v-btn>
    </v-app-bar>

    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    //
  }),
};
</script>
