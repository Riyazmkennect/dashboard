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
      :items="desserts"
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
          { text: 'issue', value: 'issue' },
          { text: 'created', value: 'created' },
          { text: 'status', value: 'status' },
          { text: 'weekCount', value: 'weekCount' },
          { text: 'clousreRate', value: 'clousreRate' },
          { text: ' RatioNI ', value: ' RatioNI ' },
          { text: ' year ', value: ' year ' },
         
        ],



        desserts: [
          {
            name: 'ayeza',
            issue: 'PR',
            created: '12 jan',
            status:'open',
            weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
          },
          
            {
            name: 'Misha',
            issue: 'bug',
            created: '16 jan',
            status:'close',
           
          },
            {
            name: 'rahul',
            issue: 'error',
            created: '12 june',
            status:'open',
            weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
          },
            {
            name: 'tarun',
            issue: 'component changes',
            created: '2 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'ajay',
            issue: 'pull error',
            created: '12 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'ayeza',
            issue: 'PR',
            created: '12 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'mehra',
            issue: 'PR',
            created: '28 jan',
            status:'close',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'amirza',
            issue: 'merge ',
            created: '12 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'sidharth',
            issue: 'PR',
            created: '21 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'nanda',
            issue: 'PR',
            created: '16 jan',
            status:'close',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'sandy',
            issue: 'PR',
            created: '19 jan',
            status:'open',
           
          },
            {
            name: 'ahmed',
            issue: 'error in code',
            created: '8 jan',
            status:'open',
           
          },
            {
            name: 'sumit',
            issue: 'PR',
            created: '22 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'Riyaz',
            issue: 'PR',
            created: '22 jan',
            status:'open',
           
          },
            {
            name: 'gupta',
            issue: 'PR',
            created: '24 jan',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'salman',
            issue: 'PR',
            created: '16 jun',
            status:'close',
           
          },
            {
            name: 'vidya',
            issue: 'bug',
            created: '9 jan',
            status:'close',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'azra',
            issue: 'PR',
            created: '12 aug',
            status:'open',
           
          },  {
            name: 'aliya',
            issue: 'PR',
            created: '12 sept',
            status:'open',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'disha',
            issue: 'PR',
            created: '12 jan',
            status:'close',
             weekCount:"40",
            clousreRate:"60",
             RatioNI:"6 TO 4"
           
          },
            {
            name: 'ayeza',
            issue: 'PR',
            created: '12 jan',
            status:'open',
           
          },
            {
            name: 'sunny',
            issue: 'PR',
            created: '12 oct',
            status:'open',
           
          },
            {
            name: 'sohail',
            issue: 'PR',
            created: '12 aug',
            status:'open',
           
          },
            {
            name: 'honey',
            issue: 'PR',
            created: '12 jan',
            status:'open',
           
          },
            {
            name: 'mark',
            issue: 'PR',
            created: '12 jan',
            status:'close',
           
           },
         
       ],
      }
    },
  }
</script>