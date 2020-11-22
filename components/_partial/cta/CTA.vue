<template>
    <button  
        :name="cta.value" 
        :title="cta.value" 
        :value="cta.value" 
        class="btn btn-signup rounded-pill">
        {{cta.value}} <img src="~/assets/img/next.svg" />
    </button>
</template>

<script>
export default {
  name: 'CTA', 
  props: {
        cta: {
            type: Object,
            required: true
        }
    }
}
</script>