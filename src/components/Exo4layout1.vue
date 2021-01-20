<template>
    <div class="exo4">
        <div class="title1 title">
            <slot name="title">Title 01 from layout 1</slot>
        </div>
       <p>
           Lorem ipsum dolor sit amet consectetur adipisicing elit. Enim fugiat totam exercitationem, laboriosam magni illum cupiditate vel modi nobis quo omnis perspiciatis consequatur quod amet, quaerat asperiores corporis odio a.
       </p>
    </div>    
</template>

<script>
export default {
    name: "Exo4layout1",
}
</script>

<style lang="stylus" scoped>
@import '../theme.styl';

.exo4{
    background-color #ccc;
    color: #333;
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
    background-color red;
}
.exo4 .title2{
    background-color navy;
    color: #fff;
}

</style>