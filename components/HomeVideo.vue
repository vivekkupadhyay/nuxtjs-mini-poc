<template>
    <section class="video-section wavy-divider mb-0">
        <div class="container">
            <video width="100%" controls
                :src="videoContent.videoURL" 
                :poster="videoContent.posterURL">
                Sorry, your browser doesn't support embedded videos, 
                but don't worry, you can <a :href="videoContent.videoURL">download it</a> 
                and watch it with your favorite video player!
            </video>
        </div>
    </section>
</template>

<script>
export default {
    name: 'homeVideo', 
    props: {
        videoContent: {
            type: Object,
            required: true
        }
    }
}
</script>