<template>
  <v-container>
    <v-card>
      <v-data-table :headers="headers" :items="desserts" class="elevation-1 products-table">
        <template v-slot:item.glutenfree>
          От 1 шт
          <v-btn class="mx-1" fab depressed small dark color="#D04802">
            <v-icon dark>fa-shopping-basket</v-icon>
          </v-btn>
        </template>
        <template v-slot:item.iron="{item}" }>
          {{item.iron}}
          <v-tooltip top>
            <template v-slot:activator="{ on }">
              <v-btn icon v-on="on">
                <v-icon small>far fa-question-circle</v-icon>
              </v-btn>
            </template>
            <span>От 100 000 ₽ скидки</span>
          </v-tooltip>
        </template>
      </v-data-table>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    desserts: [
      {
        name: "zeta24435",
        calories: "1 ПКВТ(б)-3",
        fat: "Концевая",
        carbs: 240,
        protein: "Под заказ",
        iron: "2545₽",
      },
      {
        name: "zeta24425",
        calories: "1 ПСТ(б)-3 нг-Ls",
        fat: "Соединительная",
        carbs: 240,
        protein: "Под заказ",
        iron: "2159.2₽",
      },
      {
        name: "zeta24436",
        calories: "1 ПКВТ(б)-3",
        fat: "Концевая",
        carbs: 300,
        protein: "Под заказ",
        iron: "3395.2₽",
      },
      {
        name: "zeta24426",
        calories: "1 ПСТ(б)-3 нг-Ls",
        fat: "Соединительная",
        carbs: 300,
        protein: "Под заказ",
        iron: "2452.2₽",
      },
      {
        name: "zeta24437",
        calories: "1 ПКВТ(б)-3",
        fat: "Концевая",
        carbs: 400,
        protein: "Под заказ",
        iron: "3561.3₽",
      },
      {
        name: "zeta24427",
        calories: "1 ПСТ(б)-3 нг-Ls",
        fat: "Соединительная",
        carbs: 400,
        protein: "Под заказ",
        iron: "2513.7₽",
      },
      {
        name: "zeta24438",
        calories: "1 ПКВТ(б)-3",
        fat: "Концевая",
        carbs: 500,
        protein: "Под заказ",
        iron: "3815.6₽",
      },
      {
        name: "zeta24425",
        calories: "1 ПСТ(б)-3 нг-Ls",
        fat: "Соединительная",
        carbs: 500,
        protein: "Под заказ",
        iron: "3253.2₽",
      },
      {
        name: "zeta24435",
        calories: "1 ПКВТ(б)-3",
        fat: "Концевая",
        carbs: 630,
        protein: "Под заказ",
        iron: "4003.3₽",
      },
      {
        name: "zeta24425",
        calories: "1 ПСТ(б)-3 нг-Ls",
        fat: "Соединительная",
        carbs: 630,
        protein: "Под заказ",
        iron: "3482.8₽",
      }
    ],
    headers: [
      { text: "Артикул", value: "name" },
      { text: "Тип изделия", value: "calories" },
      { text: "Тип муфты", value: "fat" },
      { text: "Сечение кабеля, мм2", value: "carbs" },
      { text: "Остаток", value: "protein" },
      { text: "Цена", value: "iron" },
      { text: "Купить", value: "glutenfree" }
    ]
  })
};
</script>

<style scoped>
.products-table /deep/ th {
  color: black !important;
}
</style>