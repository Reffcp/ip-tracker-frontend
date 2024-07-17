<template>
  <v-container>
    <v-row no-gutters>
      <v-col align-self="center">
        <h2 class="text-center">Localizador de IPs</h2>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="8">
        <v-text-field
          :rules="rulesIP"
          hide-details="auto"
          label="Ingrese la dirección IP"
        ></v-text-field>
        <v-btn block color="primary">Buscar</v-btn>
      </v-col>
    </v-row>

    <v-row>
      <v-col cols="12">
        <MapComponent />
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
const rulesIP = [
  (v) => !!v || "El campo es requerido",
  (v) =>
    (v && v.length >= 7) || "La dirección IP debe tener al menos 7 caracteres",
];
</script>
