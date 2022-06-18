<template>
  <v-card>
    <v-card-title>
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="Numbers"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script>
import axios from "axios";

export default {
  name: "Repository",
  data() {
    return {
      repos: null,
      search: "",
      details:[],
      headers: [
        {
          text: "Number",
          align: "start",
          sortable: false,
          value: "name",
        },
        { text: " id", value: "items.id" },
        // { text: "name", value: "name" },
        { text: "Created At", value: "items.created_at" },
        { text: "total_count", value: "total_count" },
        // { text: "week count", value: "week count" },
        // { text: "closure Rate", value: "closure Rate" },
        // { text: "Year", value: "Year" },     
         ],
         Numbers:[]
    };
  },

  created: function () {
    axios
      .get(
        "https://api.github.com/search/issues?q={query}{&page,per_page,sort,order}"
      )
      .then((response) => {
        this.repos = response.data;
        this.details=response.data;
      });
  },
 
};
</script>