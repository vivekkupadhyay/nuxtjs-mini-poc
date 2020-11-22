<template>
    <section class="hero-section if-blue-bg text-center">
        <div class="container">
            <h1>{{ heroContent.heading }}</h1>
            <div v-html="heroContent.copyText" class="section-content"></div> 
            <CTA :cta="ctaContent.cta" />
        </div>
    </section>
</template>

<script>
import CTA from './_partial/cta/CTA'
export default {
    name: 'heroSection', 
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
        heroContent: {
            type: Object,
            required: true
        }, 
        ctaContent: {
            type: Object,
            required: true
        }
    }
}
</script>
