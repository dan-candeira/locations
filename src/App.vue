<script setup>
import Place from './components/Place.vue';

const locations = [
  {
    name: 'moscow',
    img: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/moscow.svg',
    desc: `Moscow is the capital and most populous city of Russia, with 13.2 million residents within the city limits and 17.8 million within the urban area. Moscow has the status of a Russian federal city.`,
  },
  {
    name: 'paris',
    img: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/paris1.svg',
    desc: `Paris is the capital and most populous city of France. By the 17th century, Paris was one of Europe's major centres of finance, commerce, fashion, science, and the arts, and it retains that position still today.`,
  },
  {
    name: 'rome',
    img: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/rome.svg',
    desc: `Rome's history spans more than 2,500 years. While Roman mythology dates the founding of Rome at around 753 BC, the site has been inhabited for much longer, making it one of the oldest continuously occupied sites in Europe.`,
  },
  {
    name: 'paris',
    img: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/paris2.svg',
    desc: `By the end of the 12th century, Paris had become the political, economic, religious, and cultural capital of France. Maurice de Sully undertook the construction of the Notre Dame Cathedral at its eastern extremity.`,
  },
];
</script>

<template>
  <div>
    <main>
      <h1>Your Upcoming Destinations</h1>

      <div class="location-contain">
        <article
          class="locations"
          v-for="location in locations"
          :key="location.img"
        >
          <Place :location="location">
            <h2>{{ location.name }}</h2>
          </Place>
        </article>
      </div>
    </main>
  </div>
</template>

<style lang="scss">
*,
*::before,
*::after {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
body {
  width: 100%;
  height: 100vh;
  font-family: 'NTR', sans-serif;
  background: #eee;
}

h1 {
  text-align: center;
  margin-bottom: 2rem;
}
#app {
  padding: 1rem 0;
}

.location-contain {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 35ch), 1fr));
  grid-auto-rows: 32rem;
  place-items: center;
  grid-gap: 2rem;
  gap: 2rem;

  max-width: 75rem;
  width: 85%;
  margin: 0 auto;

  .locations {
    display: flex;
    flex-direction: column;
    justify-content: center;

    height: 100%;

    background: white;
    border: 1px solid #ddd;
    padding: 20px 20px;

    > * + * {
      margin-block-start: 0.8rem;
    }

    h2 {
      text-align: center;
    }

    img {
      margin: 10px;
      align-self: center;
    }
  }
}

</style>
