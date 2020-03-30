<template>
    <section class="page-section" id="contact">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2 class="section-heading text-uppercase">Связь с нами</h2>
                    <h3 class="section-subheading text-muted">Lorem ipsum dolor sit amet consectetur.</h3>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <form id="contactForm" name="sentMessage" @submit.prevent="submit" novalidate>
                        <div class="row">
                            <div class="col-md-6">
                                <div class="form-group" :class="{ 'form-group--error': $v.form.name.$error }">
                                    <input class="form-control"
                                           id="name"
                                           type="text"
                                           placeholder="Имя *"
                                           v-model="form.name">
                                    <div class="error text-white" v-if="!$v.form.name.required">Введите имя</div>
                                    <div class="error text-white" v-if="!$v.form.name.minLength">Введите не менее {{$v.form.name.$params.minLength.min}} букв.</div>
                                </div>
                                <div class="form-group" :class="{ 'form-group--error': $v.form.email.$error }">
                                    <input class="form-control"
                                           id="email"
                                           type="email"
                                           placeholder="Email *"
                                           v-model.trim="$v.form.email.$model">
                                    <div class="error text-white" v-if="!$v.form.email.required">Введите email</div>
                                    <div class="error text-white" v-if="!$v.form.email.minLength">Введите не менее {{$v.form.email.$params.minLength.min}} символов.</div>
                                    <div class="error text-white" v-if="!$v.form.email.email">Введите email</div>
                                </div>
                                <div class="form-group" :class="{ 'form-group--error': $v.form.phone.$error }">
                                    <input class="form-control"
                                           id="phone"
                                           type="tel"
                                           placeholder="Телефонный номер *"
                                           v-model.trim="$v.form.phone.$model">
                                    <div class="error text-white" v-if="!$v.form.phone.required">Введите телефонный номер</div>
                                    <div class="error text-white" v-if="!$v.form.phone.minLength">Введите не менее {{$v.form.phone.$params.minLength.min}} символов.</div>
                                </div>
                            </div>
                            <div class="col-md-6">
                                <div class="form-group" :class="{ 'form-group--error': $v.form.message.$error }">
                                    <textarea class="form-control"
                                              id="message"
                                              placeholder="Сообщение *"
                                              v-model.trim="$v.form.message.$model">
                                    </textarea>
                                    <div class="error text-white" v-if="!$v.form.message.required">Введите сообщение</div>
                                    <div class="error text-white" v-if="!$v.form.message.minLength">Введите не менее {{$v.form.message.$params.minLength.min}} символов.</div>
                                </div>
                            </div>
                            <div class="clearfix"></div>
                            <div class="col-lg-12 text-center">
                                <div id="success"></div>
                                <button id="sendMessageButton"
                                        class="btn btn-primary btn-xl text-uppercase"
                                        type="submit"
                                        :disabled="form.submitStatus === 'PENDING'">
                                    Send Message
                                </button>
                                <p class="typo__p text-white" v-if="form.submitStatus === 'OK'">Спасибо!</p>
                                <p class="typo__p text-white" v-if="form.submitStatus === 'ERROR'">Пожалуйста заполните верно.</p>
                                <p class="typo__p text-white" v-if="form.submitStatus === 'PENDING'">Отправка...</p>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
  import { required, minLength, email } from 'vuelidate/lib/validators'
  export default {
    name: "Contact",
    data(){
      return {
        form: {
          name: '',
          email: '',
          phone: '',
          message: '',
          submitStatus: null
        }
      }
    },
    validations: {
      form: {
        name: {
          required,
          minLength: minLength(4)
        },
        email: {
          required,
          minLength: minLength(4),
          email
        },
        phone: {
          required,
          minLength: minLength(9)
        },
        message: {
          required,
          minLength: minLength(10)
        }
      }
    },
    methods: {
      submit() {
        console.log('submit!');
        this.$v.$touch();
        if (this.$v.$invalid) {
          this.form.submitStatus = 'ERROR'
        } else {
          // submit logic here
          this.form.submitStatus = 'PENDING';
          setTimeout(() => {
            this.form.submitStatus = 'OK'
          }, 500)
        }
      }
    },
  }
</script>

<style scoped>

</style>