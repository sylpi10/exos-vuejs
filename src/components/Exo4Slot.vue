<template>
    <div class="exo4">
    <header>
    <slot name="title"></slot>
  </header>
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