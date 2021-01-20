<template>
    <div class="exo5">
        <button> 
        Consume API </button>
    </div>    
</template>

<script>

export default {
    name: "BoutonAxios",
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