<template>
  <v-app>
    <v-app-bar app color="#D04802"></v-app-bar>

    <v-content>
      <Properties />
      <ProductsTable />
    </v-content>
  </v-app>
</template>

<script>
import Properties from "./components/Properties";
import ProductsTable from "./components/ProductsTable";

export default {
  name: "App",

  components: {
    Properties,
    ProductsTable
  },

  data: () => ({
    //
  })
};
</script>
