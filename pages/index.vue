<template>
  <section>
    <Hero :heroContent="heroContent" :ctaContent="ctaContent" />
    <HomeVideo :videoContent="videoContent" />
    <OfferDetais :offerDetailsContent="offerDetailsContent" />
    <Testimonials :testimonialsContent="testimonialsContent" />
    <FinalSignup :finalSignupContent="finalSignupContent" />
    <EndCTA :ctaContent="ctaContent" />
  </section>
</template>

<script>
import axios from "~/node_modules/axios";
import Hero from "@/components/Hero";
import HomeVideo from "@/components/HomeVideo";
import OfferDetais from "@/components/OfferDetails";
import Testimonials from "@/components/Testimonials";
import FinalSignup from "@/components/FinalSignup";
import EndCTA from "@/components/EndCTA";

export default {
  name: "home",
  components: {
    Hero,
    HomeVideo,
    OfferDetais,
    Testimonials,
    FinalSignup,
    EndCTA,
  },
  data: function () {
    return {
      heroContent: {
        heading: "",
        copyText: "",
      },
      videoContent: {
        videoURL: "",
        posterURL: "",
      },
      offerDetailsContent: {
        heading: "",
        copyText: "",
      },
      testimonialsContent: {
        heading: "",
        hzCards: [],
        vtCards: [],
      },
      finalSignupContent: {
        heading: "",
        copyText: "",
      },
      ctaContent: {
        cta: {
          value: "",
          url: "",
        },
      },
    };
  },
  async fetch() {
    var md = require("markdown-it")();

    const siteContent = await axios.get(`https://ddsitecontentapi-test-01.azurewebsites.net/api/v1.0/into-future/page?identifierToken=/home&locale=en-US`);

    // props binding to child components
    if (siteContent.data.headings) {
      siteContent.data.headings.forEach((item, index) => {
        if (item.contentSlug == "campaign-ee-launch-landing-h1") {
          //Hero heading
          this.heroContent.heading = item.value;
        } else if (item.contentSlug == "campaign-ee-launch-landing-section1-h2") {
          //OfferDetails heading
          this.offerDetailsContent.heading = item.value;
        } else if (item.contentSlug == "campaign-ee-launch-landing-section2-h2") {
          //Testimonials heading
          this.testimonialsContent.heading = item.value;
        } else if (item.contentSlug == "campaign-ee-launch-landing-section3-h2") {
          //FinalSignup heading
          this.finalSignupContent.heading = item.value;
        }
      });
    }
    if (siteContent.data.textBlocks) {
      siteContent.data.textBlocks.forEach((item, index) => {
        if (item.contentSlug == "campaign-ee-launch-landing-intro") {
          //Hero copyText
          this.heroContent.copyText = md.render(item.value);
        } else if (item.contentSlug == "campaign-ee-launch-landing-section1-copy") {
          //OfferDetails copyText
          this.offerDetailsContent.copyText = md.render(item.value);
        } else if (item.contentSlug == "campaign-ee-launch-landing-section3-copy") {
          //FinalSignup copyText
          this.finalSignupContent.copyText = md.render(item.value);
        }
      });
    }
    if (siteContent.data.callsToAction) {
      siteContent.data.callsToAction.forEach((item, index) => {
        if (item.contentSlug == "campaign-ee-launch-sign-up") {
          this.ctaContent.cta.url = item.url;
          this.ctaContent.cta.value = item.value;
        }
      });
    }

    //HomeVideo Content
    if (siteContent.data.videos) {
      siteContent.data.videos.forEach((item, index) => {
        if (item.contentSlug == "campaign-ee-launch-hero-video") {
          this.videoContent.videoURL = item.video.cloudinaryVideo.url;
          this.videoContent.posterURL = item.video.previewImage.url;
        }
      });
    }

    //Testimonial Cards(hz/vt)
    if (siteContent.data.cards) {
      siteContent.data.cards.forEach((item, index) => {
        this.testimonialsContent.hzCards.push(item);
      });
    }
    if (siteContent.data.cardSets) {
      siteContent.data.cardSets[0].cards.forEach((item, index) => {
        this.testimonialsContent.vtCards.push(item);
      });
    }
  },
};
</script>