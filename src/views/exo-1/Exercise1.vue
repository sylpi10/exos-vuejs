<template>
  <div class="exercise-1">
    <h3>Bienvenue, {{ firstname }} {{ lastname }}!</h3>
    <h3>Bienvenue, {{ firstname +" "+ lastname  }}!</h3>
    <h3>Bienvenue, {{ `${firstname} ${lastname}` }}!</h3>

    <hr>
    <p>
      Enter your firstname
    <input type="text" v-model="name">
    <!-- <button type="submit">Submit</button> -->
    </p>
    <h3>Welcome {{ name }}</h3>
    <hr>
    <p>How old are you ?</p>
    <input type="number" name="" id="" v-model="age">
    <div v-if="age != 0">
        <h3 v-if="age > 18"> You are {{ age }}, you're a grown up !!</h3>
        <h3 v-else> You are {{ age }}, you're still young !!</h3>
        <h4>You were born in {{ (currentDate - age) -1 }}</h4>
    </div>
    <hr>

  </div>
</template>

<script>
export default {
  name: "Exercise1",
  data() {
    return {
      firstname: "Anne",
      lastname: "Trotreau",
      name: "",
      age: 0,
      currentDate: new Date().getFullYear()
    };
  },

};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-1 h1 {
  color: $grey;
}
.exercise-1 hr {
  width: 30%;
  margin:60px auto;
  opacity: .4;
}
.exercise-1 button {
  background-color: green;
  color: #fff;
  border: none;
  padding:4px 10px;
  margin-left: 30px;
}
</style>
