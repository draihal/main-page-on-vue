<template>
    <section class="page-section" id="services">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2 class="section-heading text-uppercase">Направления</h2>
                    <h3 class="section-subheading text-muted">Lorem ipsum dolor sit amet consectetur.</h3>
                </div>
            </div>
            <div class="row text-center">
                <div class="col-md-4" v-for="(obj, key) in servicesJSON" :key="key">
                    <span class="fa-stack fa-4x">
                        <i class="fas fa-circle fa-stack-2x text-primary"></i>
                        <i :class="obj.faIcon"></i>
                    </span>
                    <h4 class="service-heading">{{ obj.title }}</h4>
                    <p class="text-muted">{{ obj.text }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
  export default {
    name: "Services",
    data: () => ({
      servicesJSON: [
        {
          faIcon: 'fas fa-shopping-cart fa-stack-1x fa-inverse',
          title: 'Онлайн магазины',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit.'
        },
        {
          faIcon: 'fas fa-laptop fa-stack-1x fa-inverse',
          title: 'Дизайн',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit.'
        },
        {
          faIcon: 'fas fa-lock fa-stack-1x fa-inverse',
          title: 'Web Безопасность',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit.'
        }
      ]
    })
  }
</script>

<style scoped>

</style>