<template >
   <div class="m-10">
        <DataTitle :text="title" :dataDate ="dataDate" />
    <DataBoxs :stats = "stats" />
    <CountrySelect @get-country="getCountryData" :countries = "countries" />
   </div>
</template>

<script>
import DataTitle from '../components/DataTitle'
import DataBoxs from '../components/DataBoxs'
import CountrySelect from '../components/CountrySelect'

export default {
    name:'Home',
    components:{
        DataTitle,
        DataBoxs,
        CountrySelect
    },
    data(){
        return{
            title:'Global',
            dataDate:'',
            country:'',
            stats: {},
            countries :[],

        }
    },
    methods:{
        async fetchCovidData(){

            const res = await fetch('https://api.covid19api.com/summary')
            const data = await res.json()
            return data

             
        },
      
        getCountryData(country){
            this.stats = country
            this.title = country.Country
        },

       
        
    },
    async created(){
        const data = await this.fetchCovidData()
      
        console.log(data)
         

      
        this.dataDate = data.Date
        this.stats = data.Global
        this.countries = data.Countries
        // console.log(this.countries[0].Country)
        // console.log(this.countries.map(country=>[country.NewDeaths]))
        //  let s= this.countries.map(country => (country))
       
    }
}
</script>