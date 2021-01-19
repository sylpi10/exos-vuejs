<template>
  <div class="exercise-2">
    <div class="card" v-for="(user, index) in users" :key="index">
      <h2>{{ user.firstname }} {{ user.lastname }}</h2>
      <h3>{{ getFullName }}</h3>
      <h3> {{ user.email }} </h3>
      <h4> {{ user.password }} </h4>
      <!-- <img v-bind:src="`https://picsum.photos/id/ ${user.id} /200/300`" alt=""> -->
      <img v-bind:src="`https://loremflickr.com/280/160?random= ${user.id}`" alt="">
          
      <h5 v-if="user.premium"> Is premium </h5>
      <button @click="changeStatus(index)">Premium status</button>
    </div>
  </div>
</template>

<script>
import {users} from "./data.js";
export default {
  name: "Exercise2",
  data() {
    return {
     users: users
    };
  },
  computed: {

  },
  methods: {
    changeStatus: function(index) {
        let user = this.users[index];
        return user.premium ? user.premium = false : user.premium = true;
          // if (this.users[index].premium != true) {
          //   return this.users[index].premium = true;
          // }else if (this.users[index].premium == true) {
          //   return this.users[index].premium = false;
          // }
    },

  },
  //  beforeMount(){
  //   this.getFullName()
//  },

};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';


.exercise-2 {
  width: 74%;
  display: flex;
  justify-content: space-around;
  margin: auto;
}
.exercise-2 .card{
  width: 300px;
  border solid 1px #ccc;
  border-radius: 12px;
}
.exercise-2 .card h2{
  width: 100%;
  background-color: lightblue;
  margin:0;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
  padding:10px 0;
}

.exercise-2 .card h5{
  background-color: gold;
  width: 50%;
  margin: 12px auto;
  padding: 4px 8px;
}
.exercise-2 .card button{
  margin 20px;
  background-color lightgreen;
  border none;
  padding 8px 12px;
  border-radius 6px;
}
</style>
