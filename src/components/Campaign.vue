<template>
    <main role="main">
        <section class="jumbotron text-center">
        <div class="container">
          <h1 class="jumbotron-heading">2019 Spring Ford Flag Football</h1>
          <p class="lead text-muted">Etiam tristique lacus ut tortor suscipit accumsan. Aliquam aliquam nisl felis, bibendum tempus velit rutrum quis. In metus nulla, ullamcorper vel venenatis nec, finibus nec mauris. Vestibulum in metus nisi. </p>
          <p>
            <a href="#" class="btn btn-primary my-2 mr-2">General Monetary Donation</a>
            <a href="#" class="btn btn-secondary my-2">Other Donation</a>
          </p>
          <h3>Total Funding: {{ totalPledgedValue }}</h3>
        </div>
      </section>
      
      <div class="album py-5 bg-light" id="app">
        <div class="container">
          <div class="row">
            <SponsorItem 
                v-for="item in supportList"
                v-bind:item="item"
                v-bind:key="item.id">
            </SponsorItem>
          </div>
        </div>
      </div>
    </main>
</template>

<script>
import SponsorItem from './SponsorItem.vue'

export default {
    data() {
        return {
          supportList: [
              { id: 0, image: '/images/donation-1.png', description: 'Maecenas dapibus egestas velit, vel consequat nisi venenatis tempus. Sed sit amet lorem pulvinar, tempus ipsum ut, malesuada ligula. ', funded: 1000, target: 1000, donors: 12 },
              { id: 1, image: '/images/donation-2.png', description: 'Vivamus vel vulputate tortor, vel facilisis arcu. Mauris vitae purus urna.', funded: 1000, target: 2000, donors: 6 },
              { id: 2, image: '/images/donation-3.jpg', description: 'Maecenas dapibus egestas velit, vel consequat nisi venenatis tempus. Sed sit amet lorem pulvinar, tempus ipsum ut, malesuada ligula. ', funded: 6500, target: 4000, donors: 3 },
              { id: 3, image: '/images/donation-4.jpg', description: 'Vivamus vel vulputate tortor, vel facilisis arcu. Mauris vitae purus urna.', funded: 1950, target: 4000, donors: 6 },
              { id: 4, image: '/images/donation-5.jpg', description: 'Mauris efficitur efficitur arcu vel fringilla. Sed varius commodo turpis eget pellentesque.', funded: 750, target: 800, donors: 9 }
          ]
      }
    },
  name: 'Campaign',
  components: {
    SponsorItem
  },
  computed: {
    totalPledgedValue: function() {
      return (this.supportList.reduce((sum, item) => sum + item.funded, 0));
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .card-body .progress {
    margin: 10px 0 15px
  }
</style>
