<template>
    <section class="offerdetails-section section-padding wavy-divider mb-0">
        <div class="container text-center">
            <h2 class="section-title">{{ offerDetailsContent.heading }}</h2>
            <div v-html="offerDetailsContent.copyText" class="section-content"></div> 
        </div>
    </section>
</template>

<script>
export default {
    name: 'offerDetailsSection', 
    props: {
        offerDetailsContent: {
            type: Object,
            required: true
        }
    }
}
</script>