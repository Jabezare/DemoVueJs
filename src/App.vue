<style>
body {
  background-color: antiquewhite;
}

.display-2 {
  margin: auto;
  padding: 15px;
  width: 30%;
  border: 3px solid black;
}
</style>

<template>
  <div class="text-xs-center">
    <div class="display-2">
      Demo oldal
    </div>
    <div class="text-xs-center">
      <v-btn
        v-if="!chip1 && !chip2 && !chip3 && !chip4"
        class="headline"
        color="primary"
        dark
        @click="chip1 = true, chip2 = true, chip3 = true, chip4= true">
        Reset Chips
      </v-btn>
    </div>

    <v-chip 
      v-model="chip1"
      class="headline"
      close>A Jedlik</v-chip>

    <v-chip
      v-model="chip2"
      class="headline"
      close
      color="red"
      text-color="white">egy</v-chip>

    <v-chip
      v-model="chip3"
      class="headline"
      close
      color="green"
      outline>jó</v-chip>

    <v-chip
      v-model="chip4"
      class="headline"
      close
      color="purple"
      label
      outline>iskola</v-chip>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class App extends Vue {
  private chip1: boolean = true;
  private chip2: boolean = true;
  private chip3: boolean = true;
  private chip4: boolean = true;
}
</script>
