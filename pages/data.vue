 <template>
  <div class="mb-6">
    <section class="hero is-medium is-primary is-bold mb-6">
      <div class="hero-body">
        <div class="container"></div>
      </div>
    </section>
    <div class="container">
      <div class="table-container">
        <table class="table is-bordered is-striped is-hoverable is-fullwidth">
          <thead>
            <tr>
              <th>ID</th>
          
              <th>Title of issue</th>
              <th>created_at</th>
              <th>open issue</th>
              <th>close issue</th>
              <th>closure rate</th>
              <!-- <th>closure Rate</th> -->
            </tr>
          </thead>
          <tbody>
            <tr v-for="repo in repos" v-bind:key="repo.id">
              <td>{{ repo.id }}</td>
              <td>{{ repo.description }}</td>
              <td>{{ repo.created_at }}</td>
              <td>{{ repo.open_issues }}</td>
              <th>{{repo.watchers}}</th>
              <th>{{repo.size}}</th>
              <!-- <td>{{ repo. }}</td> -->
            </tr>
          </tbody>
        </table>
        <button @click="move()">move</button>
        <button @click="previous()">previous</button>
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
      repos: [],
      page: 1
    };
  },

  created: function () {
    this.getData();
  },
  methods: {
    async getData() {
      const { data } = await axios.get(
        `https://api.github.com/users/octocat/repos?per_page=100&page=${this.page}`
      );
      this.repos = data;
      console.log(this.repos);
      const arr=data%data
    },

    previous() {
      if (this.page == 1) return;
      this.page--;
      this.getData();
    },
    move() {
      this.page++;
      this.getData();
    },
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
