<template>
  <div class="exercise-5">
    <aside class="aside">
    <h1>Exo 5</h1> 
    <BoutonAxios class="axiosBtn" @click.native="consume()">
    </BoutonAxios>
    <div class="" v-if="!isEditing">
      <form action="" class="form" method="POST">
        <span>Add a resto</span>
        <input type="text" v-model="nom" placeholder="nom" value="">
        <input type="text" v-model="type" placeholder="type" value="">
        <input type="text" v-model="adresse" placeholder="adresse"  value="">
        <input type="text" v-model="telephone" placeholder="tel" value="">
        <input type="text" v-model="plats" placeholder="plats" value="">
        <button @click.prevent="sendPost()">Add</button>
      </form>
    </div>

    <div v-else>
      <form class="form">
        <span>Update resto {{id}} </span>
         <input type="text" v-model="nom" placeholder="nom" value="">
        <input type="text" v-model="type" placeholder="type" value="">
        <input type="text" v-model="adresse" placeholder="adresse"  value="">
        <input type="text" v-model="telephone" placeholder="tel" value="">
        <input type="text" v-model="plats" placeholder="plats" value="">
        <button  @click.prevent="updateResto(id)"> Save </button>
        <button v-on:click="cancelEdit(movie['.key'])">Cancel</button>
      </form>
    </div>

    </aside>

      <div class="wrapper">

      <Vignette v-for="resto in info" :key="resto.id">
           <template v-slot:name>
            <h1>
              {{resto.nom}}
            </h1>
          </template>
           <template v-slot:type>
            {{resto.type}}
          </template>
           <template v-slot:image>
            <img :src="`${resto.image}`" alt="">  
          </template>
           <template v-slot:address>
             {{resto.adresse}}
          </template>
           <template v-slot:tel>
             {{resto.telephone}}
          </template>
           <template v-slot:plats>
             <div class="plats">
          <hr>
             {{resto.plats}}
             </div>
          </template>
          <template v-slot:buttons>
            <div class="btns">
              <button class="update" @click="toUpdate(resto.id)">Update</button>
              <button class="delete"
                @click.prevent="deleteResto(resto.id)"
              > X </button>
            </div>
          </template>
      </Vignette>

      </div>
  </div>
</template>

<script>
import BoutonAxios from "../../components/BoutonAxios.vue";
import Vignette from "../../components/Vignette.vue";
import axios from 'axios';
export default {
  components: { BoutonAxios, Vignette },
  name: "Exercise5",
  data() {
    return {
      info: [],
      id: 0,
      nom: "",
      type: "",
      adresse: "",
      telephone: "",
      plats: "",
      isEditing: false
    }
  },
   methods: {
    // consume: function () {
    //   axios
    //     .get('https://restop-toulouse.herokuapp.com/restos')
    //     .then(response => (this.info = response.data))
    // },
    async consume() {
  // GET request using axios with async/await
    const response = await axios.get("https://restop-toulouse.herokuapp.com/restos");
    this.info = response.data;
  },
    sendPost() {
      const postData = { nom: this.nom, type: this.type, adresse: this.adresse,
       telephone: this.telephone, plats: this.plats};
      axios
        .post("https://restop-toulouse.herokuapp.com/restos", postData)
        .then(res => {
          console.log(res.data);
          this.consume(); 
        });
    },
    deleteResto(idToDelete) {
     axios
      .delete(`https://restop-toulouse.herokuapp.com/restos/${idToDelete}`)
      .then((response) => {
        console.log(response)
    })
    .catch((error) => {
      console.log(error);
    });
    },
    toUpdate(idToUpdate){
      this.isEditing = true;
      this.id = idToUpdate;
    },
    updateResto(idToUpdate){
       this.id = idToUpdate;
       const putData = {idToUpdate: this.id, nom: this.nom, type: this.type, adresse: this.adresse,
       telephone: this.telephone, plats: this.plats};
       axios
        .put(`https://restop-toulouse.herokuapp.com/restos/${idToUpdate}`, putData)
        .then((response) => {
        console.log(response)
          this.nom = '',
          this.type = '',
          this.adresse = '',
          this.telephone = '',
          this.plats = '',
          this.isEditing = false
         this.consume(); 
    })
    }
   }
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-5{
  display flex;
}
.aside{
  display flex;
  flex-direction column;
  justify-content space-around;
  height 400px;
  background-color lightblue;
  position: fixed;
}
.form{
  display flex;
  flex-direction column;
}
.form input{
  margin 10px;
}
.wrapper{
  display flex;
  width 80%;
  margin auto;
  margin-right: -80px;
  flex-wrap wrap;
}
.vignette{
  border solid 1px #ccc;
  width 300px;
  margin 20px;
}
.vignette h1{
  width 100%;
  background-color: lightblue;
  margin-top 0;
  padding 10px 0;
}
.vignette h2{
  font-size 1.4rem;
}
.plats{
  font-size 1.5rem;
  margin-top 40px;
  padding 20px;
}
.btns{
  margin 8px;
  display flex;
  justify-content space-around;
}
.btns button{
  border: none;
  padding 4px 12px;
  border-radius: 8px;
  cursor pointer;
}
.btns button:hover{
  opacity: .7;
}
.btns .update{
  background-color lightgreen;
}
.btns .delete{
  background-color red;
  color: #fff;
}
</style>
