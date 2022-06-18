 <template>
  <div class="mb-6">
    <section class="hero is-medium is-primary is-bold mb-6">
      <div class="hero-body">
        <div class="container">
        </div>
      </div>
    </section>
    <div class="container">
      <div class="table-container">
        <table class="table is-bordered is-striped is-hoverable is-fullwidth">
          <thead>
            <tr>
            
              <th>Number</th>
              <th>Title of issue</th>
              <th>Status</th>
              <th>created_at</th>
              <th>open issue count </th>
              <th>Close issue</th>
              <th>Closure Rate</th>
              <th>open issues</th>
            </tr>
          </thead>
          <tbody>
             <tr v-for="repo in repos" v-bind:key="repo.id">
             
               <td>{{ repo.number }}</td>
                 <td>{{ repo.title }}</td>  
                 <td>{{ repo.state }}</td>
               <td>{{ repo.created_at }}</td>
               <th>{{repos.open_issues_count}}</th>
               <th>{{repos.watchers_count}}</th>
               <th>{{repos.open_issues}}</th>

              
             
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
    };
  },
   created:function(){
    let array=[]
    const  getData=async()=>{
    for(let i=1;i<=40;i++){
      const {data}=await axios.get(`https://api.github.com/users/octocat/repos?per_page=100&state=all&direction=asc,page${i}`) 
      array.push(...data)
      // console.log(array)
      // https://api.github.com/repos/axios/axios/issues?per_page=100&state=all&direction=asc,page
      
    }
    this.repos=array
    console.log(this.repos)
  }
  getData()
   },
 
  closureRate(){
     count/comments
  }
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
