<template>
    <div class="exo3">
        <button type="submit"
        :class="{ red: hasError, green: green }"
        > {{ title }}</button>
        <p class="error-text" v-if="hasError">{{ error }}</p>
    </div>    
</template>

<script>
export default {
    name: "Button",
    props:{
    hasError: {
      type: Boolean,
      default: false
    },
    error: {
      type: String,
      default: 'there is an error'
    },
    green: {
      type: Boolean,
      default: true
    },
    title: {
      type: String,
      default: 'btn title'
    }    
  }
}
</script>

<style lang="stylus" scoped>
@import '../theme.styl';

.exo3 button{
    width: 320px;
    background-color: #fff;
    color: #aaa;
    padding 12px;
    border: solid #333 2px;
    margin-top 30px;
    text-transform uppercase;
}
.exo3 .red{
    border: solid red 2px;
}
.exo3 .green{
    background-color: green;
    color #fff;
}
.exo3 .error-text{
    color: orange;
}
</style>