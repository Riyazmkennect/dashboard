<!-- <template>
  <div> -->
    <!-- <p v-if="$fetchState.pending">Fetching mountains...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <h1>Nuxt Mountains</h1>
      <ul>
        <li v-for="mountain of mountains" :key="mountain">{{ mountain.title }}</li>
      </ul>
      <button @click="$fetch">Refresh</button>
    </div> -->
    <!-- <h1>{{ mountain.title }}</h1>
    
  </div>
</template>

<script>
  export default {
    data() {
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/mountains'
      ).then(res => res.json())
    }
  }
</script> -->



<template>
  <div class="mb-6">
    <section class="hero is-medium is-primary is-bold mb-6">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">Get GitHub Repositories</h1>
        </div>
      </div>
    </section>
    <div class="container">
      <div class="table-container">
        <table class="table is-bordered is-striped is-hoverable is-fullwidth">
          <thead>
            <tr>
              <th>Number</th>
              <th>Issue</th>
              <th>Status</th>
              <th>Created At</th>
              <th>clousre Rate monthly</th>
              <th>year</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="repo in repos" v-bind:key="repo.id">
              <td>{{ repo.id }}</td>
              <td>{{ repo.name }}</td>
              <td>{{ repo.html_url }}</td>
              <td>{{ repo.language }}</td>
              <td>{{ repo.owner.login }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Repository",
  data() {
    return {
      repos: null,
      details:[]
    };
  },
  created: function () {
    axios.get("https://api.github.com/users/riyazulahad786/repos").then((response) => {
      this.details=response.data;
      this.repos = response.data;
    });
  },
};
</script>

<style>
body {
  font: 15px/1.8 "Poppins", sans-serif !important;
}
.table td,
.table th {
  padding: 20px !important;
}
</style>