<template>
  <div class="home">
    <v-container>
      <v-row justify="center">
        <v-col sm="6">
          <v-simple-table>
            <template v-slot:default>
              <thead>
                <tr>
                  <th class="text-left">Name</th>
                  <th class="text-left">Calories</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in products" :key="item.Name">
                  <td>{{ item.Name }}</td>
                  <td>
                    <img
                      :src="baseUrl + item.Image.formats.thumbnail.url"
                      :alt="item.Name"
                      :height="item.Image.formats.thumbnail.height"
                    />
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-col>
        <v-col sm="6">
          <v-form>
            <v-container>
              <v-row>
                <v-col cols="12">
                  <v-text-field
                    v-model="name"
                    label="Outlined"
                    outlined
                    clearable
                  ></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-file-input
                    chips
                    multiple
                    outlined
                    label="File input w/ chips"
                  ></v-file-input>
                </v-col>
                <v-col cols="12">
                  <v-btn class="mr-4" type="submit"> submit </v-btn>
                  <v-btn @click="clear"> clear </v-btn>
                </v-col>
              </v-row>
            </v-container>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import axios from "axios";
export default {
  name: "Home",
  methods: {
    clear() {},
  },
  data: () => ({
    name: "",
    desserts: [
      {
        name: "Frozen Yogurt",
        calories: 159,
      },
      {
        name: "Ice cream sandwich",
        calories: 237,
      },
      {
        name: "Eclair",
        calories: 262,
      },
      {
        name: "Cupcake",
        calories: 305,
      },
      {
        name: "Gingerbread",
        calories: 356,
      },
      {
        name: "Jelly bean",
        calories: 375,
      },
      {
        name: "Lollipop",
        calories: 392,
      },
      {
        name: "Honeycomb",
        calories: 408,
      },
      {
        name: "Donut",
        calories: 452,
      },
      {
        name: "KitKat",
        calories: 518,
      },
    ],
    products: null,
    baseUrl: "http://localhost:1337",
  }),
  mounted() {
    axios.get(this.baseUrl + "/products").then((response) => {
      this.products = response.data;
      console.log(response.data);
    });
  },
};
</script>
