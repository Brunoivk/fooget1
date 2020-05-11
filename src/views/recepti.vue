 <!--  -->
 
<template>
  <div class="naslovnica">
<h1>RECEPTI</h1>
<h1>prikaz svih recepata</h1>
    <h2>Dodaj novi recept</h2>
    
    <div class="upis">
      <input v-model="naziv" type="text" id="fname"><br>
      <button @click="dodaj">Dodaj</button>
    </div>
    <button v-on:click="count++">You clicked me {{ count }} times.</button>
    <div>{{naziv}}</div>
      <div class="row">     
       
       <div class="col-3">    1. stupac svi RECEPTI <karticerecepata/> <karticerecepata/> <karticerecepata/> <!-- nmg onako ispisati ko na naslovnici jer nemam polje ovdje -->
 </div>    
          
          <div class="col-3">      2. stupac svi RECEPTI <karticerecepata/><karticerecepata/> <karticerecepata/>  </div> 
          

           <div class="col-3">      3. stupac svi <karticerecepata/> <karticerecepata/> <karticerecepata/>  </div> 
           <div class="col-3">      3. stupac svi <karticerecepata/> <karticerecepata/> <karticerecepata/>  </div> 
           </div>
     </div>
  
  
</template>
<script>
import karticerecepata from '@/components/karticerecepata.vue'
export default {
  name:"naslovnica",
  components: {
    karticerecepata
  },
  data(){
    return{
       naziv: "pero",
      recept:[],
       count: 0

    }
    
  },
  methods:{
    dodaj(){
      this.recept.push({
        naziv: this.naziv
      })
    }
  }

}
</script>

