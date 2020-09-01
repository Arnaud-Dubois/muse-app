<template>
  <div>
  <div class="container">

    <!-- Logo -->
    <TheLogo
      class="relative md:absolute top-0 left-0 ml-8"
      style="width: 60px"
    />
    <!-- / Logo -->

    <!-- Header -->
    <header class="header w-full bg-black mb-20">
      <!-- <div class="flex flex-col md:flex-row">
        <div class="w-full md:w-1/2 p-6">
          <h1 class="text-4xl pt-16">A futuristic look at the past</h1>
          <p class="text-2xl">Education to future-proof your life</p>

          <BaseButton class="mt-6">Explore</BaseButton>
          <BaseButton class="mt-6" border>Museums</BaseButton>
        </div>
        <div class="w-full md:w-1/2">
          <img src="~/static/images/angel-header.png" alt="angel" width="100%" height="100%">
        </div>
      </div> -->

      <div class="relative p-8">

        <div class="relative md:absolute flex flex-col justify-center w-full md:w-1/2 pl-0 md:pl-40 h-full">
          <h1 class="text-4xl">A futuristic look at the past</h1>
          <p class="text-2xl py-10">Visit museums, learn about history and meet new people to share your experience with !</p>
          <div>
            <BaseButton class="mt-6 mr-2">Explore</BaseButton>
            <BaseButton class="mt-6" border>Museums</BaseButton>
          </div>
        </div>
        <div class="w-full overflow-hidden">
          <BabylonScene/>    
        </div>

      </div>

    </header>
    <!-- / Header -->

    <!-- How does it works -->
    <BaseSection color class="px-6 py-40">
      <h2 class="text-6xl font-bold">How Musa works</h2>
      <div class="flex flex-col md:flex-row justify-center mt-24">
        <FrameCard
          class="mb-8 md:mb-0"
          :key="card.title"
          v-for="card in cards"
          :step="card.step"
          :title="card.title"
        >
          {{ card.text }}
        </FrameCard>
      </div>
    </BaseSection>
    <!-- / How does it works -->

    <!-- State of the Art -->
    <BaseSection :image="'images/state-of-the-art.jpg'">
      <div class="container p-6 py-40">
        <h2 class="text-4xl font-bold mb-8">State of the art<br> at your fingertips</h2>
        <p class="text-2xl mb-8">
          MUSA is an application for YOU to access art and culture freely in one single swoop.<br>
          Just download the app and start visiting thousand years of history.
        </p>
        <BaseButton>
          <!-- <font-awesome-icon :icon="['fas', 'download']"/> -->
          <DownloadIcon class="inline w-8 h-8"/>
          <span class="align-text-top">Download</span>
        </BaseButton>
      </div>
    </BaseSection>
    <!-- / State of the Art -->

    <!-- An immersive experience -->
    <BaseSection color :image="'images/naissance-venus.png'">
      <div class="flex flex-col-reverse md:flex-row">

        <div class="w-full md:w-1/2 bg-purple-test point-tile text-left py-40 p-6">
          <div class="w-full md:w-1/2 mx-auto">
            <h2 class="text-4xl font-bold mb-8">An immersive<br> Experience</h2>
            <p class="text-2xl mb-8">
              Thanks to the VR technology, our museums provides an unique way of discovering the state of the art
            </p>
            <BlackButton>
              <a class="decoration-none" href="https://www.museumnext.com/article/how-museums-are-using-virtual-reality/" target="_blank">
                <span class="mr-3 align-text-top">Learn more about VR</span>
                <ExternalLinkIcon class="inline"/>
              </a>
            </BlackButton>
          </div>
          
        </div>

        <div class="w-full md:w-1/2 relative text-left">
          <WhiteCard class="relative md:absolute w-full md:w-3/4 h-3/4 mt-0 md:mt-10 ml-0 md:-ml-8">
            <h3 class="text-5xl mb-0 md:mb-32">Tangible knowledge</h3>
            <BigNumber class="relative md:absolute" number="1."/>
          </WhiteCard>
          <img class="absolute bottom-0 right-0 w-2/3" src="images/vr-headset-guy.png" alt="VR guy" width="100%" height="100%">
        </div>

      </div>
    </BaseSection>
    <!-- / An immersive experience -->

    <!-- Museums Tour -->
    <BaseSection class="py-40 museum-tour">
      <h2 class="text-5xl font-bold mb-24">Museums Tour</h2>
      <div class="flex flex-col-reverse md:flex-row container text-2xl">
        <div class="w-full md:w-1/3">
          <img class="mx-auto" src="~/static/images/girl_alone_illu.svg" alt="girl watching phone">
          <p class="p-8">Watch what the parkour of others musers and follow their instructions about the plan.</p>
        </div>
        <div class="w-full md:w-1/3">
          <img class="mx-auto" src="~/static/images/man_alone_illu.svg" alt="man watching phone">
          <p class="p-8">Add your personal touch to others experience and share it !</p>
        </div>
        <div class="w-full md:w-1/3">
          <img class="mx-auto" src="~/static/images/girl_man_illu.svg" alt="girl and man sharing">
          <p class="p-8">Discuss with other Musers and start to visit again !</p>
        </div>
      </div>
    </BaseSection>
    <!-- / Museums Tour -->

    <!-- Find your way -->
    <BaseSection color class="py-40 px-8">
      <div class="container">
        <div class="flex flex-col-reverse md:flex-row flex-wrap md:flex-no-wrap">
          <div class="w-full md:w-1/2 ">
            <!-- <GraphPhone class="w-full"/> -->
            
            <div
              style="max-width: 478px; max-height: 814px"  
              class="bg-white rounded-lg p-6 shadow-2xl"
            >
              <div class="w-full h-full rounded-lg overflow-hidden relative">
                <MapMarkerIcon style="top: 10%; left: 30%" class="absolute color-main"/>
                <MapMarkerIcon style="top: 50%; left: 45%" class="absolute color-main"/>
                <MapMarkerIcon style="top: 70%; left: 80%" class="absolute color-main"/>
                <img class="max-w-none" src="~/static/images/map_find_your_way.jpg" alt="map" width="964" height="844">
              </div>
            </div>
          </div>
          <div class="w-full md:w-1/2">
            <div class="text-left">
              <h2 class="base-section-title font-bold">Find your way</h2>
              <h3 class="text-3xl md:text-6xl font-bold">Filter by type or by location your favorite museum.</h3>
            </div>
          </div>
        </div>
      </div>
    </BaseSection>
    <!-- / Find your way -->

    <!-- Form: filter your search -->
    <!-- <BaseSection :image="'images/louvre.png'">
      <div class="flex flex-col-reverse md:flex-row h-screen py-40">

        <div class="w-full md:w-1/2">
          <WhiteCard class="text-left w-full md:w-auto relative md:absolute top-0 left-0 m-0 md:m-24">
            <h3 class="text-5xl font-bold">Filter your search</h3>
            <form>
              
              <div class="my-4">
                <label class="block" for="">Type of museum</label>
                <input type="text" class="p-3 border border-purple-400 rounded-full">
              </div>
              
              <div class="my-4">
                <label class="block" for="">Location</label>
                <input type="text" class="p-3 border border-purple-400 rounded-full">
              </div>

              <BaseButton>Find a museum</BaseButton>

            </form>
          </WhiteCard>
        </div>
        
        <div class="w-full md:w-1/2">
          <h2 class="text-6xl font-bold">Find your way</h2>
        </div>
      </div>
    </BaseSection> -->
    <!-- / Form: filter your search -->

    <!-- Testimonials -->
    <BaseSection :image="'images/naissance-venus.png'">
      <div class="py-40">
        <h2 class="text-4xl font-bold">What the Musers says</h2>
        <div class="container px-8 mx-auto">
          <Testimonial/>
        </div>
      </div>
    </BaseSection>
    <!-- / Testimonials -->

    <!-- Download links -->
    <BaseSection color class="pt-40 pb-20 p-6">
      <h2 class="text-4xl font-bold">Download the App</h2>
      <h5 class="text-2xl mb-8">Choose your support</h5>
      <!-- <BlackButton class="mb-4">Google Play</BlackButton> -->
      <a href="#" target="_blank" class="inline-block mx-auto">
        <img src="~/static/images/android_google_play.png" alt="Get it on Google play" width="192">
      </a>
      
    </BaseSection>
    <!-- / Download links -->

  </div>
  
  <!-- Footer -->
  <TheFooter/>
  </div>
</template>

<script>
import BabylonScene from '~/components/BabylonScene'
import BaseButton from '~/components/BaseButton'
import BlackButton from '~/components/BlackButton'
import BaseCard from '~/components/BaseCard'
import FrameCard from '~/components/FrameCard'
import WhiteCard from '~/components/WhiteCard'
import BaseSection from '~/components/BaseSection'
import BulletPoint from '~/components/BulletPoint'
import GraphPhone from '~/components/GraphPhone'
import Testimonial from '~/components/Testimonial'
import BigNumber from '~/components/BigNumber'
import TheLogo from '~/components/TheLogo'
import TheFooter from '~/components/TheFooter'

import DownloadIcon from '~/components/icons/DownloadIcon'
import ExternalLinkIcon from '~/components/icons/ExternalLinkIcon'
import MapMarkerIcon from '~/components/icons/MapMarkerIcon'

export default {
  components: {
    BabylonScene,
    BaseButton,
    BlackButton,
    BaseCard,
    FrameCard,
    WhiteCard,
    BaseSection,
    BulletPoint,
    GraphPhone,
    Testimonial,
    BigNumber,
    TheLogo,
    TheFooter,
    DownloadIcon,
    ExternalLinkIcon,
    MapMarkerIcon
  },
  data() {
    return {
      cards: [
        {step: "1", title: 'Connect', text:'Download the App from the store and install it !'},
        {step: "2", title: 'Find it', text: 'Search for your preferred style of museum on the map.'},
        {step: "3", title: 'Enjoy', text: 'Visit your museum and tell other musers about your experience.'}
      ]
    }
  }
}
</script>

<style lang='scss'>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

// Colors
$bg-color-main: #05070C;
$main-color: #5F19DD;;
/* #AA50F0; */
/* #5F19DD; */
$main-gradient: linear-gradient(180deg, #8610FC 0%, #AA50F0 100%), #AA50F0;
$text-white: white;
$text-color: #ACACAC;

// Fonts
$main-font: 'Montserrat', sans-serif;
$sub-font: 'Galdeano', sans-serif;


.bg-main {
  background-color: $main-color;
}
.bg-main-gradient {
  background: $main-gradient;
}
.border-main {
  border-color: $main-color;
}
.color-main {
  color: $main-color;
}

body {
  background-color: $bg-color-main;
  background-color: black;
  font-family: $main-font;
  color: $text-color;
}

h1 {
  color: $text-white;
  font-size: 4rem;
  font-weight: bold;
  text-transform: uppercase;
}

h2 {
  text-transform: uppercase;
}

p {
  font-family: $sub-font;
}

.container {
  margin: 0 auto;
  text-align: center;
}

.container-fullwidth {
  width: 100vw;
  position: relative;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.content-center-y {
  position: absolute;
  top: 50%;
}
</style>
