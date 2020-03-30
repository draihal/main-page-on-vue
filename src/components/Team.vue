<template>
    <section class="bg-light page-section" id="team">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2 class="section-heading text-uppercase">Our Amazing Team</h2>
                    <h3 class="section-subheading text-muted">Lorem ipsum dolor sit amet consectetur.</h3>
                </div>
            </div>
            <div class="row">


                <div class="col-sm-4" v-for="(user, key) in usersJSON" :key="key">
                    <div class="team-member">
                        <img class="mx-auto rounded-circle" :src="user.img" alt="">
                        <h4>{{ user.name }}</h4>
                        <p class="text-muted">{{ user.role }}</p>
                        <ul class="list-inline social-buttons">
                            <li class="list-inline-item">
                                <a :href="user.linkToTwitter">
                                    <i class="fab fa-twitter"></i>
                                </a>
                            </li>
                            <li class="list-inline-item">
                                <a :href="user.linkToFacebook">
                                    <i class="fab fa-facebook-f"></i>
                                </a>
                            </li>
                            <li class="list-inline-item">
                                <a :href="user.linkToLinkedin">
                                    <i class="fab fa-linkedin-in"></i>
                                </a>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-8 mx-auto text-center">
                    <p class="large text-muted">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aut eaque, laboriosam veritatis, quos non quis ad perspiciatis, totam corporis ea, alias ut unde.</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
  export default {
    name: "Team",
    data: () => ({
      usersJSON: [
        {
          name: 'Галина Широкая',
          role: 'Преподаватель курса по Python',
          img: require('../assets/img/team/1.jpg'),
          linkToTwitter: '#',
          linkToFacebook: '#',
          linkToLinkedin: '#'
        },
        {
          name: 'Федор Иванов',
          role: 'Преподаватель курса по Web',
          img: require('../assets/img/team/2.jpg'),
          linkToTwitter: '#',
          linkToFacebook: '#',
          linkToLinkedin: '#'
        },
        {
          name: 'Валентина Высоцкая',
          role: 'Преподаватель курса по Java',
          img: require('../assets/img/team/3.jpg'),
          linkToTwitter: '#',
          linkToFacebook: '#',
          linkToLinkedin: '#'
        }
      ]
    })
  }
</script>

<style scoped>

</style>