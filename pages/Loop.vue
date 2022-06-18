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
              <th>Number</th>
              <th>Title of issue</th>
              <th>Status</th>
              <th>created_at</th>
              <th>closure rate</th>
              <!-- <th>closure Rate</th> -->
            </tr>
          </thead>
          <tbody>
            <tr v-for="repo in repos" v-bind:key="repo.id">
              <td>{{ repo.id }}</td>
              <td>{{ repo.number }}</td>
              <td>{{ repo.title }}</td>
              <td>{{ repo.state }}</td>
              <td>{{ repo.created_at }}</td>
              <td>{{repo.comments}}</td>
              <!-- <td>{{ repo. }}</td> -->
            </tr>
          </tbody>
        </table>
        <button id="move" @click="move()">move</button>
        <button id="previous" @click="previous()">previous</button>
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
        `https://api.github.com/repos/axios/axios/issues?per_page=100&page=${this.page}`  
      );
      this.repos = data;
      console.log(this.repos);
      
    },
    // https://api.github.com/repos/axios/axios/issues?per_page=100&page=1&state%3Dall&direction%3Dasc,page

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
#previous{
  color: aqua;
}
#move{
  color: blue;
}
</style> 



<!-- async function getRepos() {
    const url = "THEURL"
    const headers = {
        "Authorization": `Token temppp`
    }
    const response = await fetch(url, {
        "method": "GET",
        "headers": headers
    })
    const result = await response.json()
    console.log(result)
    
    const temp = []
    result.items.forEach(i => {
        temp.push(i.name);
    })
    console.log(temp)

} -->