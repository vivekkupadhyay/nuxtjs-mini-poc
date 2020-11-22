<template>
    <section class="finalsignup-section section-padding">
        <div class="container text-center">
            <h2 class="section-title">{{ finalSignupContent.heading }}</h2>
            <div v-html="finalSignupContent.copyText" class="section-content"></div> 
        </div>
    </section>
</template>

<script>
export default {
    name: 'finalSignup', 
    props: {
        finalSignupContent: {
            type: Object,
            required: true
        }
    }
}
</script>