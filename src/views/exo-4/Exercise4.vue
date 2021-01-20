<template>
  <div class="exercise-4">
    <main :class="{'newClass': isAddClass}">

    <h1>Exo 4</h1>
    <BoutonSlot class="btn">
        <span @click="clicked()">Btn slot</span>
    </BoutonSlot>
    <BoutonSlot class="btn">
        <span @click="clicked()">Btn slot 02</span>
    </BoutonSlot>
    <BoutonSlot class="btn">
    </BoutonSlot>
    
    <hr>

      <h2>4.2</h2>   
      <Exo4Slot>  
          <template v-slot:title>
            <h1>Named slots</h1>
          </template>
        <template v-slot:title2>
          <h1>Named slots 02</h1>
        </template>
        <template v-slot:slot-btn>
          <span v-on:click="addClass">Btn</span>
        </template>
        <template v-slot:para>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos alias aspernatur eaque similique obcaecati! Quisquam rerum doloremque itaque et, soluta tempora provident vitae fugiat, recusandae officiis non sint error? Ullam.</p>
        </template>
      </Exo4Slot> 

    <hr>
      <h2>4.3</h2>
    <nav class="navbar">
        <button @click="selectedComponent = 'Exo4layout1'" class="nav-item">One</button>
        <button @click="selectedComponent = 'Exo4layout2'" class="nav-item">Two</button>
    </nav>

    <component :is="selectedComponent">
    </component>

     </main>
  </div>
</template>

<script>
import BoutonSlot from "../../components/BoutonSlot.vue";
import Exo4Slot from "../../components/Exo4Slot.vue";
import Exo4layout1 from "../../components/Exo4layout1.vue";
import Exo4layout2 from "../../components/Exo4layout2.vue";

export default {
  components: { BoutonSlot, Exo4Slot, Exo4layout1, Exo4layout2 },

  name: "Exercise4",
  data() {
    return {
      isAddClass: false,
      selectedComponent: 'Exo4layout1'
    }
  },
  methods: {
    clicked: function() {
    alert("clicked");  
   },
   addClass: function() {
      this.isAddClass = true;
  }
}

}
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-4 .btn{
  margin 30px;
}
.exercise-4 p{
  width 50%;
  margin 20px auto;
  border: solid 1px #bbb;
  padding 12px;
}
.exercise-4 .newClass {
      box-shadow: 0px 0px 5px #000; 
      background-color: navy;
      padding: 3px 5px;
}

.exercise-4 .title{
    width: 500px;
    margin:20px auto;
    padding 4px;
}
.exercise-4 .title1{
    background-color #ff0;
}
.exercise-4 .navbar{
    display flex;
    justify-content space-around;
    width: 50%;
    margin 20px auto;
}
.exercise-4 .navbar .nav-item{
   width 60px;
   background-color #333;
   color yellow;
   cursor pointer;
   padding 4px 10px;
   border-radius 6px;
}
.exercise-4 .navbar .nav-item:hover{
   opacity .7;
}

</style>
