<template>
  <v-app id="inspire">
    <v-toolbar>
      <v-toolbar-side-icon />
      <v-toolbar-title>Jedlik Vuetify Starter</v-toolbar-title>
      <v-spacer />
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          flat 
          @click="OnClick('Link One')">Link One</v-btn>
        <v-btn
          flat
          @click="OnClick('Link Two')">Link Two</v-btn>
        <v-btn
          flat
          @click="OnClick('Link Three')">Link Three</v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-form>
      <v-container>
        <v-layout
          row
          wrap>
          <v-flex
            xs12
            sm6
            md3
            ld3
            xl3>
            <v-text-field label="Regular" />
            <v-text-field
              label="Regular"
              placeholder="Placeholder" />
            <v-text-field 
              label="Solo" 
              solo />
            <v-text-field 
              label="Solo" 
              placeholder="Placeholder" 
              solo />
            <v-text-field 
              label="Box" 
              box />
            <v-text-field 
              label="Box" 
              placeholder="Placeholder" 
              box />
            <v-text-field 
              label="Outline" 
              outline />
            <v-text-field 
              label="Outline" 
              placeholder="Placeholder" 
              outline />
          </v-flex>
  
  
          <v-flex 
            xs12 
            sm6 
            md3 
            ld3 
            xl3>
            <v-textarea 
              v-model="longText" 
              name="i71" 
              label="Default style" 
              hint="Hint text" />
            <v-textarea 
              v-model="longText" 
              solo 
              name="i74" 
              label="Solo textarea" />
            <v-textarea 
              v-model="longText" 
              box 
              name="i75" 
              label="Box textarea" />
            <v-textarea 
              v-model="longText" 
              outline 
              name="i76" 
              label="Outline textarea" />
          </v-flex>
  
          <v-flex 
            xs12 
            sm6 
            md3 
            ld3 
            xl3>
            <v-btn color="success">Success</v-btn>
            <v-btn color="error">Error</v-btn>
            <v-btn color="warning">Warning</v-btn>
            <v-btn color="info">Info</v-btn>
            <v-checkbox
              v-model="checkbox"
              :label="`Checkbox 1: ${checkbox.toString()}`" />
            <v-radio-group v-model="radioGroup">
              <v-radio 
                v-for="n in 3" 
                :key="n" 
                :label="`Radio ${n}`" 
                :value="n" />
            </v-radio-group>
            <v-switch 
              v-model="switch1"
              :label="`Switch 1: ${switch1.toString()}`" />
            <v-select 
              :items="items2" 
              label="Standard" />
            <v-select 
              :items="items2" 
              box 
              label="Box style" />
            <v-select 
              :items="items2" 
              label="Outline style" 
              outline />
            <v-select 
              :items="items2" 
              label="Solo field" 
              solo />
          </v-flex>

          <v-flex 
            xs12 
            sm6 
            md3 
            ld3 
            xl3>
            <v-pagination 
              v-model="page" 
              :length="6" />
            <v-slider 
              v-model="slider" 
              label="slider" />
            <v-card>
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
                aspect-ratio="2.75" />
      
              <v-card-title primary-title>
                <div>
                  <h3 class="headline mb-0">Kangaroo Valley Safari</h3>
                  <div>Located two hours south of Sydney in the <br>Southern Highlands of New South Wales, ...</div>
                </div>
              </v-card-title>
      
              <v-card-actions>
                <v-btn 
                  flat 
                  color="orange">
                  Share</v-btn>
                <v-btn 
                  flat 
                  color="orange">Explore</v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>

          <v-flex 
            xs12 
            sm12 
            md12 
            ld12 
            xl6>
            <v-carousel>
              <v-carousel-item 
                v-for="(item,i) in items" 
                :key="i" 
                :src="item.src" />
            </v-carousel>
          </v-flex>

          <v-flex 
            xs12 
            sm12 
            md12 
            ld12 
            xl6>
            <v-data-table 
              :headers="headers" 
              :items="desserts" 
              hide-actions 
              class="elevation-1">
              <template 
                slot="items" 
                slot-scope="props">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">{{ props.item.iron }}</td>
              </template>
            </v-data-table>
          </v-flex>
  
        </v-layout>
      </v-container>
    </v-form>

    <v-footer 
      color="grey darken-1" 
      dark>
      <v-spacer />
      <div>&copy; {{ new Date().getFullYear() }}</div>
    </v-footer>

  </v-app>
</template>

<script  lang="ts">
import { Component, Vue } from "vue-property-decorator";

interface iDesserts {
  value: boolean;
  name: string;
  calories: number;
  fat: number;
  carbs: number;
  protein: number;
  iron: string;
}

interface iSources {
  src: string;
}

interface iHeaders {
  text: string;
  align?: string;
  sortable?: boolean;
  value: string;
}

@Component
export default class Demo extends Vue {
  private checkbox: boolean = true;
  private radioGroup: number = 1;
  private switch1: boolean = true;
  private slider: number = 45;
  private page: number = 3;

  // eslint-disable-next-line
  private longText: string =
    "The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through.";

  private items2: string[] = ["Foo", "Bar", "Fizz", "Buzz"];

  private items: iSources[] = [
    { src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg" },
    { src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg" },
    { src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg" },
    { src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg" }
  ];

  private headers: iHeaders[] = [
    {
      text: "Dessert (100g serving)",
      align: "left",
      sortable: false,
      value: "name"
    },
    { text: "Calories", value: "calories" },
    { text: "Fat (g)", value: "fat" },
    { text: "Carbs (g)", value: "carbs" },
    { text: "Protein (g)", value: "protein" },
    { text: "Iron (%)", value: "iron" }
  ];

  private desserts: iDesserts[] = [
    {
      value: false,
      name: "Frozen Yogurt",
      calories: 159,
      fat: 6.0,
      carbs: 24,
      protein: 4.0,
      iron: "1%"
    },
    {
      value: false,
      name: "Ice cream sandwich",
      calories: 237,
      fat: 9.0,
      carbs: 37,
      protein: 4.3,
      iron: "1%"
    },
    {
      value: false,
      name: "Eclair",
      calories: 262,
      fat: 16.0,
      carbs: 23,
      protein: 6.0,
      iron: "7%"
    },
    {
      value: false,
      name: "Cupcake",
      calories: 305,
      fat: 3.7,
      carbs: 67,
      protein: 4.3,
      iron: "8%"
    },
    {
      value: false,
      name: "Gingerbread",
      calories: 356,
      fat: 16.0,
      carbs: 49,
      protein: 3.9,
      iron: "16%"
    },
    {
      value: false,
      name: "Jelly bean",
      calories: 375,
      fat: 0.0,
      carbs: 94,
      protein: 0.0,
      iron: "0%"
    },
    {
      value: false,
      name: "Lollipop",
      calories: 392,
      fat: 0.2,
      carbs: 98,
      protein: 0,
      iron: "2%"
    },
    {
      value: false,
      name: "Honeycomb",
      calories: 408,
      fat: 3.2,
      carbs: 87,
      protein: 6.5,
      iron: "45%"
    },
    {
      value: false,
      name: "Donut",
      calories: 452,
      fat: 25.0,
      carbs: 51,
      protein: 4.9,
      iron: "22%"
    },
    {
      value: false,
      name: "KitKat",
      calories: 518,
      fat: 26.0,
      carbs: 65,
      protein: 7,
      iron: "6%"
    }
  ];

  private OnClick(művelet: string): void {
    window.alert(művelet);
  }
}
</script>

<style scoped>
</style>
