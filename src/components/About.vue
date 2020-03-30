<template>
    <section class="page-section" id="about">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2 class="section-heading text-uppercase">About</h2>
                    <h3 class="section-subheading text-muted">Lorem ipsum dolor sit amet consectetur.</h3>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <ul class="timeline">
                        <li v-for="(obj, key) in timelineJSON" :key="key" :class="obj.timelineClass">
                            <div class="timeline-image">
                                <img class="rounded-circle img-fluid" :src="obj.img" alt="">
                            </div>
                            <div class="timeline-panel">
                                <div class="timeline-heading">
                                    <h4>{{ obj.date }}</h4>
                                    <h4 class="subheading">{{ obj.title }}</h4>
                                </div>
                                <div class="timeline-body">
                                    <p class="text-muted">{{ obj.text }}</p>
                                </div>
                            </div>
                        </li>
                        <li class="timeline-inverted">
                            <div class="timeline-image">
                                <h4>Be Part
                                    <br>Of Our
                                    <br>Story!</h4>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
  export default {
    name: "About",
    data: () => ({
      timelineJSON: [
        {
          img: require('../assets/img/about/1.jpg'),
          timelineClass: '',
          date: '2009-2011',
          title: 'Начало приключений',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt ut voluptatum eius sapiente, totam reiciendis temporibus qui quibusdam, recusandae sit vero unde, sed, incidunt et ea quo dolore laudantium consectetur!'
        },
        {
          img: require('../assets/img/about/2.jpg'),
          timelineClass: 'timeline-inverted',
          date: 'Июнь 2011',
          title: 'Выпуcк первого потока',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt ut voluptatum eius sapiente, totam reiciendis temporibus qui quibusdam, recusandae sit vero unde, sed, incidunt et ea quo dolore laudantium consectetur!'
        },
        {
          img: require('../assets/img/about/3.jpg'),
          timelineClass: '',
          date: 'Май 2012',
          title: 'Что-то еще',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt ut voluptatum eius sapiente, totam reiciendis temporibus qui quibusdam, recusandae sit vero unde, sed, incidunt et ea quo dolore laudantium consectetur!'
        },
        {
          img: require('../assets/img/about/4.jpg'),
          timelineClass: 'timeline-inverted',
          date: 'Август 2014',
          title: 'Что-то еще',
          text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt ut voluptatum eius sapiente, totam reiciendis temporibus qui quibusdam, recusandae sit vero unde, sed, incidunt et ea quo dolore laudantium consectetur!'
        },
      ]
    })
  }
</script>

<style scoped>

</style>