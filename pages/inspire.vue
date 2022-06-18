<!-- <template>
  <mainq>
    <div class="header">header</div>
    <div class="b1">box1</div>
    <div class="b2">box2</div>
    <div class="b3">box3</div>
    <div class="sidebar">sidebar</div>
    <div class="maind">main content</div>
    <div class="btm">bottom</div>
  </mainq>
</template>

<script>
export default {
  name: 'InspirePage'
}
</script>
<style>

mainq{
  width: 75%;
  margin: 50px auto;
}
.header{
  background-color: blue;
}
.b1{
  background-color: brown;
}
.b2{
  background-color: aquamarine;
}
.b3{
 background-color: aqua;
}
.sidebar{
  background-color: aquamarine;
}
.maind{
  background-color: beige;
}
.btm{
  background-color: aliceblue;
}
</style> -->

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
  export default {
    data () {
      return {
        search: '',
        headers: [
          {
            text: 'Number',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: ' issue', value: ' issue' },
          { text: 'Created At', value: 'Created At' },
          { text: 'Status', value: 'Status' },
        
        ],
        Numbers: [
          {
            name: 'Shikha',
            issue : 40,
           CreatedAt: 21,
            Status:'',
           
          },
           {
            name: 'Rohan',
            issue : '11',
           CreatedAt: '',
            Status: '',
           
          },
            {
            name: 'aliya',
            issue : '13',
           CreatedAt:'',
            Status: '',
           
          },
           {
            name: 'Syed',
           issue : '44',
           CreatedAt:'',
            Status: '',
           
          },
           {
            name: 'sumit Ranjan',
           issue : '41',
           CreatedAt: '',
            Status: '',
           
          },
           {
            name: 'Gupta',
            issue : '44',
           CreatedAt: '',
            Status: '',
           
          },
          {
            name: 'rahul',
            issue : '42',
           CreatedAt: '',
            Status: '',
           
          },
           {
            name: 'mehak',
            issue : '21',
           CreatedAt: '',
            Status: '',
           
          },
           {
            name: 'nanda',
            issue : '2',
           CreatedAt: '',
            Status: '',
           
          },
           {
            name: 'sidharth',
            issue : '1',
           CreatedAt: '',
            Status:'',
           
          },
        ],
      }
    },
  }
</script>