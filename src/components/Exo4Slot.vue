<template>
    <div class="exo4">
        <div class="title1 title">
            <slot name="title">Title 01</slot>
        </div>
        <div class="title title2">
            <slot name="title2" class="title2">Title 02</slot>
        </div>
        <button>
            <slot name="slot-btn"></slot>
        </button>
        <p>
            <slot name="para"></slot>
        </p>
    </div>    
</template>

<script>
export default {
    name: "Exo4Slot",
}
</script>

<style lang="stylus" scoped>
@import '../theme.styl';

.exo4 .title{
    width: 500px;
    margin:20px auto;
    padding 4px;
}
.exo4 .title1{
    background-color #ff0;
}
.exo4 .title2{
    background-color #f00;
    color: #fff;
}

</style>