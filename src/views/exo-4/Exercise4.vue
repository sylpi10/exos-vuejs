<template>
  <div class="exercise-4">
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

    <Exo4Slot>  
      <template v-slot:title>
    <h1>Named slots</h1>
  </template>
  <template v-slot:slot-btn>
    <span>Btn</span>
  </template>
  <template v-slot:para>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimos alias aspernatur eaque similique obcaecati! Quisquam rerum doloremque itaque et, soluta tempora provident vitae fugiat, recusandae officiis non sint error? Ullam.</p>
  </template>

    </Exo4Slot> 
  </div>
</template>

<script>
import BoutonSlot from "../../components/BoutonSlot.vue";
import Exo4Slot from "../../components/Exo4Slot.vue";

export default {
  components: { BoutonSlot, Exo4Slot },

  name: "Exercise4",
  props: {
      title: {
          type: String,
          default: "Envoyer par défaut"
      }
  },
  methods: {
    clicked: function() {
    alert("clicked");  
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
</style>
