<template>
  <div class="container">

    <!-- Header -->
    <header class="header w-full">
      <div class="flex flex-col md:flex-row">
        <div class="w-full md:w-1/2 p-6">
          <h1 class="text-4xl pt-16">A futuristic look at the past</h1>
          <p class="text-2xl">Education to future-proof your career</p>

          <BaseButton class="mt-6">Explore</BaseButton>
          <BaseButton class="mt-6" border>Museums</BaseButton>
        </div>
        <div class="w-full md:w-1/2">
          <img src="~/static/images/angel-header.png" alt="angel" width="100%" height="100%">
        </div>
      </div>
    </header>

    <!-- How does it works -->
    <BaseSection color class="px-6 py-40">
      <h2 class="text-4xl font-bold">How muse app works</h2>
      <div class="flex flex-col md:flex-row justify-center">
        <BaseCard
          :key="card.title"
          v-for="card in cards"
          :step="card.step"
          :title="card.title"
        >
          Lorem ipsum dolor amet
          vHS waistcoat
          poke meh authentic
        </BaseCard>
      </div>
    </BaseSection>

    <!-- State of the Art -->
    <BaseSection :image="'images/state-of-the-art.jpg'">
      <div class="container p-6 py-40">
        <h2 class="text-4xl font-bold mb-8">State of the art<br> at your fingertips</h2>
        <p class="text-2xl mb-8">
          MUSEAPP is an application for YOU to access art and culture freely in one single swoop. Just download the app and start visiting thousand years of history.
        </p>
        <BaseButton>Download</BaseButton>
      </div>
    </BaseSection>

    <!-- An immersive experience -->
    <BaseSection color :image="'images/naissance-venus.png'">
      <div class="flex flex-col-reverse md:flex-row">

        <div class="w-full md:w-1/2 bg-main-gradient text-left py-40 p-6">
          <h2 class="text-4xl font-bold mb-8">An immersive<br> Experience</h2>
          <p class="text-2xl mb-8">
            Thanks to the VR technology, our museums provides an unique way of discovering the state of the art
          </p>
          <BlackButton>
            <a class="decoration-none" href="https://www.museumnext.com/article/how-museums-are-using-virtual-reality/" target="_blank">
              Learn more about VR
            </a>
          </BlackButton>
        </div>

        <div class="w-full md:w-1/2 relative text-left">
          <WhiteCard class="relative md:absolute w-3/4 h-3/4 mt-0 md:mt-10 ml-0 md:-ml-8">
            <h3 class="text-3xl mb-0 md:mb-32">Tangible knowledge</h3>
            <BigNumber class="relative md:absolute" number="1."/>
          </WhiteCard>
          <img class="absolute bottom-0 right-0 w-2/3" src="images/vr-headset-guy.png" alt="VR guy" width="100%" height="100%">
        </div>

      </div>
    </BaseSection>

    <!-- Form: filter your search -->
    <BaseSection :image="'images/louvre.png'">
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
    </BaseSection>

    <!-- Testimonials -->
    <BaseSection color class="py-40">
      <h2 class="text-4xl font-bold">Testimonials</h2>
      <div class="container mx-auto">
        <Testimonial/>
      </div>
    </BaseSection>

    <!-- Museums Tour -->
    <BaseSection class="py-40">
      <div class="flex flex-col-reverse md:flex-row container">
        <div class="w-full md:w-1/2">
          <GraphPhone class="w-full"/>
        </div>
        <div class="w-full md:w-1/2">
          <h2 class="text-5xl font-bold">Museums Tour</h2>
          <BulletPoint>
            <p>Watch what the parkour of others musers and follow their instructions about the plan</p>
          </BulletPoint>
          <BulletPoint>
            <p>Add your personal touch to others experience !</p>
          </BulletPoint>
          <BulletPoint>
            <p>PROFIT !</p>
          </BulletPoint>
        </div>
      </div>
    </BaseSection>

    <!-- Download links -->
    <BaseSection color class="py-40 p-6">
      <h2 class="text-4xl font-bold">Download the App</h2>
      <h5 class="text-2xl mb-8">Choose your support</h5>
      <BlackButton class="mb-4">Google Play</BlackButton>
      <BlackButton>App Store</BlackButton>
    </BaseSection>


    <!-- Footer -->
    <footer>

    </footer>
    
  </div>
</template>

<script>
import BaseButton from '~/components/BaseButton'
import BlackButton from '~/components/BlackButton'
import BaseCard from '~/components/BaseCard'
import WhiteCard from '~/components/WhiteCard'
import BaseSection from '~/components/BaseSection'
import BulletPoint from '~/components/BulletPoint'
import GraphPhone from '~/components/GraphPhone'
import Testimonial from '~/components/Testimonial'
import BigNumber from '~/components/BigNumber'

export default {
  components: {
    BaseButton,
    BlackButton,
    BaseCard,
    WhiteCard,
    BaseSection,
    BulletPoint,
    GraphPhone,
    Testimonial,
    BigNumber
  },
  data() {
    return {
      cards: [
        {step: "1", title: 'Connect'},
        {step: "2", title: 'Find it'},
        {step: "3", title: 'Enjoy'}
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
$main-color: #AA50F0;
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
</style>
