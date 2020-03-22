<template>
  <div class="container">
    <header class="header w-full">
      <div class="flex">
        <div class="w-1/2">
          <h1>A futuristic look at the past</h1>
          <h2>Education to future-proof your career</h2>
          
          <BaseButton>Explore</BaseButton>
          <BaseButton border>Museums</BaseButton>
        </div>
        <div class="w-1/2">

          <img src="~/static/images/angel-header.png" alt="angel">

        </div>
      </div>
    </header>

    <BaseSection color class="py-40">
      <h2 class="text-5xl font-bold">How muse app works</h2>
      <div class="flex justify-center">
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

    <BaseSection :image="'images/state-of-the-art.jpg'" class="py-40">
      <div class="container">
        <h2 class="text-5xl font-bold">State of the art<br> at your fingertips</h2>
        <p class="text-2xl">
          MUSEAPP is an application for YOU to access art and culture freely in one single swoop. Just download the app and start visiting thousand years of history.
        </p>
        <BaseButton>Download</BaseButton>
      </div>
    </BaseSection>

    <BaseSection color :image="'images/naissance-venus.png'">
      <div class="flex">
        <div class="w-1/2 bg-purple-600 text-left py-40">
          <h2 class="text-5xl font-bold">AN IMMERSIVE<br> EXPERIENCE</h2>
          <p class="text-2xl">
            Thanks to the VR technology, our museums provides an unique way of discovering the state of the art
          </p>
          <BlackButton>
            <a class="decoration-none" href="https://www.museumnext.com/article/how-museums-are-using-virtual-reality/" target="_blank">
              Learn more about VR
            </a>
          </BlackButton>
        </div>
        <div class="w-1/2 relative text-left">
          <WhiteCard class="absolute w-3/4 h-3/4 mt-10 -ml-8">
            <h3 class="text-3xl mb-32">Tangible knowledge</h3>
            <BigNumber class="absolute" number="1."/>
          </WhiteCard>
          <img class="absolute bottom-0 right-0 w-2/3" src="images/vr-headset-guy.png" alt="VR guy" width="100%" height="100%">
        </div>
      </div>
    </BaseSection>

    <BaseSection :image="'images/louvre.png'" class="py-40">
      <div class="h-screen">
        <WhiteCard class="text-left absolute top-0 left-0 m-24">
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
        <h2 class="text-6xl font-bold">FIND YOUR WAY</h2>
      </div>
    </BaseSection>

    <BaseSection color class="py-40">
      <h2 class="text-5xl font-bold">Testimonials</h2>
      <div class="container mx-auto">
        <Testimonial/>
      </div>
    </BaseSection>

    <BaseSection class="py-40">
      <div class="flex container">
        <div class="w-1/2">
          <GraphPhone/>
        </div>
        <div class="w-1/2">
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

    <BaseSection color class="py-40">
      <h2 class="text-5xl font-bold">Download the App</h2>
      <h5 class="text-2xl">Choose your support</h5>
      <BlackButton>Google Play</BlackButton>
      <BlackButton>App Store</BlackButton>
    </BaseSection>
    
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
  font-family: $main-font!important;
  color: $text-color;
}

h1 {
  color: $text-white;
  font-size: 4rem;
  font-weight: bold;
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
