<template>
  <div class="exercise-3">
    <h1> Exo 3</h1>
  <Bouton
          :hasError="true"
          :error="error"
          :green="true"
          :title="title"
  > </Bouton>
  <Bouton
          :hasError="false"
          :error="error"
          :green="false"
          :title="title"
  > </Bouton>
 
  </div>
</template>

<script>
// import App from '../../App.vue';
import Bouton from "../../components/Bouton.vue";

export default {
  components: { Bouton },
  name: "Exercise3"
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-3 {
  color: $grey;
}

</style>
