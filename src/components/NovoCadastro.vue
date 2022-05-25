<template>
  <div class="text-center">
    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on, attrs }">
        <v-btn color="primary lighten-2" dark v-bind="attrs" v-on="on">
          Novo Cadastro
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 info"> Cadastro </v-card-title>

        <v-card-text>
          <v-text-field
            v-model="firstname"
            :rules="nameRules"
            :counter="10"
            label="Nome"
            required
          ></v-text-field>
          <v-text-field
            v-model="lastname"
            :rules="nameRules"
            :counter="10"
            label="Sobrenome"
            required
          ></v-text-field>
          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
          ></v-text-field>
          <v-checkbox
            v-model="checkbox"
            :rules="[(v) => !!v || 'Você deve concorda e continuar']"
            label="Você concorda!"
            required
          ></v-checkbox>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" @click="dialog = false"> Cadastra </v-btn>
          <v-btn color="secondary" @click="dialog = false"> Cancelar </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      email: "",
      emailRules: [
        (v) => !!v || "E-mail invalido",
        (v) => /.+@.+\..+/.test(v) || "o e-mail deve ser valido",
      ],
      checkbox: false,
    };
  },
};
</script>