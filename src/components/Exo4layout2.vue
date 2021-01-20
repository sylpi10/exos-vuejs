<template>
    <div class="exo4">
        <div class="title1 title">
            <slot name="title">Title 01 from layout 2</slot>
        </div>
        
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla facilis vero accusantium quos minus est sed in, laudantium minima ad velit ab aspernatur ullam eum accusamus vel consequatur odit voluptate?
        </p>
    </div>    
</template>

<script>
export default {
    name: "Exo4layout2",
}
</script>

<style lang="stylus" scoped>
@import '../theme.styl';

.exo4{
    background-color #333;
    color: #fff;
    height 30vh;
    padding-top 80px;
}
.exo4 .title{
    width: 800px;
    margin:10px auto;
    padding 14px;
    border-radius 20px;
}
.exo4 .title1{
    background-color purple;
}
.exo4 .title2{
    background-color orange;
    color: #fff;
}

</style>