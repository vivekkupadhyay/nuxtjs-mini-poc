<template>
    <section class="testimonials-section section-padding wavy-divider mb-0">
        <div class="container">
            <h2 class="section-title text-center mb-0">{{ testimonialsContent.heading }}</h2>
            <ul class="testimonials-cards hz-cards">
                <li class="card mb-3 border-0 rounded-0" v-for="hzCard in testimonialsContent.hzCards" :key="hzCard.copy">
                    <div class="row no-gutters">
                        <div class="col-md-3">
                            <img 
                                :data-src="hzCard.image.url" 
                                :alt="hzCard.image.description" 
                                :title="hzCard.image.title" 
                                class="card-img border-0 rounded-0 lazyload" />
                        </div>
                        <div class="col-md-9">
                            <div class="card-body border-0 rounded-0">
                                <div class="card-text">{{ hzCard.copy }}</div>
                                <h5 class="card-title">{{ hzCard.heading }}</h5><h6 class="card-subtitle">{{ hzCard.subHeading }}</h6>
                            </div>
                        </div>
                    </div>
                </li>
            </ul> 
            <ul class="row card-deck testimonials-cards vt-cards">
                <li class="card border-0 rounded-0" v-for="vtCard in testimonialsContent.vtCards" :key="vtCard.copy">
                    <img 
                        :data-src="vtCard.image.url" 
                        :alt="vtCard.image.description" 
                        :title="vtCard.image.title" 
                        class="card-img border-0 rounded-0 lazyload" />    
                    <h5 class="card-title">{{ vtCard.heading }}</h5><h6 class="card-subtitle">{{ vtCard.subHeading }}</h6>
                    <div class="card-body border-0 rounded-0">
                        <div class="card-text">{{ vtCard.copy }}</div>
                    </div>
                </li>
            </ul>
        </div>
    </section>
</template>

<script>
export default {
    name: 'testimonailSection', 
    props: {
        testimonialsContent: {
            type: Object,
            required: true
        }
    }
}
</script>