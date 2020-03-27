<template>
  <v-container>
    <v-card>
      <v-card-title>Муфты кабельные</v-card-title>
      <v-divider></v-divider>
      <v-card-text>
        <v-row>
          <v-col cols="4" lg="4">
            <v-card>
              <v-card-title class="title">Тип кабеля</v-card-title>
              <v-card-text class="card-text">
                <v-select v-model="cabelType" :items="types" hide-details solo></v-select>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Рабочее напряжение</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.voltage" row>
                  <v-radio label="до 6 кВ" value="radio-1"></v-radio>
                  <v-radio label="до 10 кВ" value="radio-2"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Материал изоляции</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.material" row>
                  <v-radio label="Бумага" value="radio-1"></v-radio>
                  <v-radio label="Сшитый полиэтилен" value="radio-2"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Наличие защитного слоя в кабеле</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.security" row></v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Тип муфты</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.type" row>
                  <v-radio label="Концевая" value="radio-1"></v-radio>
                  <v-radio label="Соединительная" value="radio-2"></v-radio>
                  <v-radio label="Переходная" value="radio-3"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Количество жил</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.veins" row>
                  <v-radio label="1" value="radio-1"></v-radio>
                  <v-radio label="3" value="radio-2"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Номинальное сечение жилы, мм2</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.cut" row>
                  <v-radio label="25" value="radio-1"></v-radio>
                  <v-radio label="35" value="radio-2"></v-radio>
                  <v-radio label="50" value="radio-3"></v-radio>
                  <v-radio label="70" value="radio-4"></v-radio>
                  <v-radio label="95" value="radio-5"></v-radio>
                  <v-radio label="120" value="radio-6"></v-radio>
                  <v-radio label="150" value="radio-7"></v-radio>
                  <v-radio label="185" value="radio-8"></v-radio>
                  <v-radio label="240" value="radio-9"></v-radio>
                  <v-radio label="300" value="radio-10"></v-radio>
                  <v-radio label="400" value="radio-11"></v-radio>
                  <v-radio label="500" value="radio-12"></v-radio>
                  <v-radio label="630" value="radio-13"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Наличие наконечников/соединителей</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.cap" row></v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Бренд</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.brand" row>
                  <v-radio label="ЗЭТАРУС" value="radio-1"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card>
              <v-card-title class="title">Особенности</v-card-title>
              <v-card-text class="card-text">
                <v-radio-group v-model="radioButtons.features" row>
                  <v-radio label="Комплектация РЭС Новосибирск" value="radio-1"></v-radio>
                  <v-radio label="Все" value="all"></v-radio>
                </v-radio-group>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-btn color="#d04802" dark @click="reset">Сбросить</v-btn>
        </v-row>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    cabelType: null,
    types: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
    radioButtons: {
      voltage: "all",
      material: "all",
      security: "all",
      type: "all",
      veins: "all",
      cut: "all",
      cap: "all",
      brand: "all",
      features: "all"
    }
  }),

  methods: {
    reset() {
      this.cabelType = null;
      this.radioButtons = {
        voltage: "all",
        material: "all",
        security: "all",
        type: "all",
        veins: "all",
        cut: "all",
        cap: "all",
        brand: "all",
        features: "all"
      };
    }
  }
};
</script>

<style scoped>
.title {
  color: #d04802;
  background-color: #f5f5f5;
}
.card-text {
  margin-top: 10px;
}
/** Цвет текста на radio-кнопках */
.v-radio /deep/ label {
  color: black;
}
/** Цвет иконки на radio-кнопках */
.v-radio /deep/ .fa-dot-circle {
  color: #d04802 !important;
}
</style>