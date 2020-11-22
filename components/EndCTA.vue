<template>
    <section class="endcta-section if-blue-bg text-center section-padding">
        <div class="container">
            <CTA :cta="ctaContent.cta" />
        </div>
    </section>
</template>

<script>
import CTA from './_partial/cta/CTA'
export default {
    name: 'endCTASection', 
    components: {
        CTA
    },
    data: function() {
        return {
            cta: {
              value: '', 
              url: ''
            }
        }  
    },
    props: {
        ctaContent: {
            type: Object,
            required: true
        }
    }
}
</script>
