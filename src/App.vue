<template>
  <v-app>
    <v-app-bar app color="#D04802"></v-app-bar>

    <v-content>
      <Properties />
    </v-content>
  </v-app>
</template>

<script>
import Properties from "./components/Properties";

export default {
  name: "App",

  components: {
    Properties
  },

  data: () => ({
    //
  })
};
</script>
