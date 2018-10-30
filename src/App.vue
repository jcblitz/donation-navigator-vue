<template>
  <div id="app">
    <Header /> 
    <Campaign />
    <Footer />
   </div>
</template>

<script>
  import Campaign from './components/Campaign.vue'
  import Header from './components/Header.vue'
  import Footer from './components/Footer.vue'
  

  export default {
    name: 'app',
    components: {
      Campaign,
      Header,
      Footer
    },
    mounted() {
      let jquery = document.createElement('script')
      jquery.setAttribute('src', 'https://code.jquery.com/jquery-3.3.1.slim.min.js')
      
      let popper = document.createElement('script')
      popper.setAttribute('src', 'https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js')

      let bootstrap = document.createElement('script')
      bootstrap.setAttribute('src', 'https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js')
      
      document.head.appendChild(jquery)
      document.head.appendChild(popper)
      document.head.appendChild(bootstrap)
    }
  }
</script>

<style>
@import url("https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css");
:root {
    --jumbotron-padding-y: 3rem;
  }
  
  .jumbotron {
    padding-top: var(--jumbotron-padding-y);
    padding-bottom: var(--jumbotron-padding-y);
    margin-bottom: 0;
    background-color: #fff;
  }
  @media (min-width: 768px) {
    .jumbotron {
      padding-top: calc(var(--jumbotron-padding-y) * 2);
      padding-bottom: calc(var(--jumbotron-padding-y) * 2);
    }
  }
  
  .jumbotron p:last-child {
    margin-bottom: 0;
  }
  
  .jumbotron-heading {
    font-weight: 300;
  }
  
  .jumbotron .container {
    max-width: 40rem;
  }
  
  footer {
    padding-top: 3rem;
    padding-bottom: 3rem;
  }
  
  footer p {
    margin-bottom: .25rem;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
