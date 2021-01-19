<template>
    <div class="exo4">
        <button> 
             <slot>
               Envoyer par défaut
             </slot>
        </button>
    </div>    
</template>

<script>
export default {
    name: "BoutonSlot",
    props: {
        title: {
            type: String,
            default: "Envoyer par défaut"
        }
    }
  
}
</script>