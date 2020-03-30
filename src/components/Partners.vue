<template>
    <section class="py-5">
        <div class="container">
            <infinite-slide-bar :barStyle="{ padding: '5px 0' }">
                <img v-for="(obj, key) in clientsJSON" :key="key" :src="obj.logo" alt="">
            </infinite-slide-bar>
        </div>
    </section>
</template>

<script>
  import InfiniteSlideBar from 'vue-infinite-slide-bar'

  export default {
    name: "Clients",
    components: { InfiniteSlideBar },
    data: () => ({
      clientsJSON: [
        {
          logo: require('../assets/img/logos/envato.jpg'),
          href: '#'
        },
        {
          logo: require('../assets/img/logos/designmodo.jpg'),
          href: '#'
        },
        {
          logo: require('../assets/img/logos/themeforest.jpg'),
          href: '#'
        },
        {
          logo: require('../assets/img/logos/creative-market.jpg'),
          href: '#'
        },
      ]
    })
  }
</script>

<style scoped>
</style>