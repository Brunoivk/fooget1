<template>
  <div class="naslovnica">
<h1>naslovnica</h1>
      <div class="row">     
       
       <div class="col-4">    1. stupac ZADNJE DODANI RECEPTI <karticerecepata v-for="k in filter" :info="k" :key="k.id" /> 
 </div>    
          
          <div class="col-4">      2. stupac NASUMICNI RECEPTI <karticerecepata v-for="k in filter" :info="k" :key="k.id" /> </div> 
          

           <div class="col-4">      3. stupac  S NAJVIŠE KOMENTARA ILI NAJBOLJI <karticerecepata v-for="k in filter" :info="k" :key="k.id" />  </div> 
           </div>
     </div>
  
  
</template>
<script>
import karticerecepata from '@/components/karticerecepata.vue' 
import store from '@/store.js'
export default {
  name:"naslovnica",
  components: {
    karticerecepata
  },
  data(){
    return{
      kartice: [ {   // svaki objekt ima kljuceve naslov,vrijeme,url
        naslov: "jedan",
        vrijeme: "prije mjesec dana",
        url: "/bolonjez-sa-gljivama.jpg"
      },
      { naslov: "dva",
        vrijeme: "prije 2 mjeseca ",
         url:  "https://picsum.photos/id/2/400/400"
      },
      { naslov: "tri",
        vrijeme: "prije 3 mjeseca ",
         url: "https://picsum.photos/id/3/400/400"
      }
              
          
             
      ]

    }
    
  },
  computed: {
      filter(){
        return this.kartice.filter(k => 
        k.naslov.includes(store.terminalpretrage) || k.vrijeme.includes(store.terminalpretrage))
      }
    }
}
</script>