<template>
    <div class="vignette">
            <slot name="name">
            </slot>
        <h2> 
            <slot name="type">
            </slot>
        </h2>
        <div class="">
            <slot name="image"> </slot>
        </div>
        <address>
            <slot name="address"> </slot>
        </address>
        <span>
            <slot name="tel"> </slot>
        </span>    
        <div>
            <slot name="plats"> </slot>
        </div>    
        
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