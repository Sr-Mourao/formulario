<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <h3>Empresa Ltda Mourão's</h3>
      </div>

      <v-spacer></v-spacer>
      <NovoCadastro />

      
    </v-app-bar>

    <v-main></v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import NovoCadastro from "./components/NovoCadastro.vue"

export default {
  name: "App",

  components: {
    HelloWorld,
    NovoCadastro,
},

  data: () => ({
    //
  }),
};
</script>
