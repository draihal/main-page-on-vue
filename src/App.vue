<template>
  <div id="app">
    <Navbar></Navbar>
    <MainScreen></MainScreen>
    <Services></Services>
    <Courses></Courses>
    <About></About>
    <Team></Team>
    <Partners></Partners>
    <Contact></Contact>
    <Footer></Footer>
  </div>
</template>

<script>

  import Courses from "./components/Courses";
  import Navbar from "./components/Navbar";
  import MainScreen from "./components/MainScreen";
  import Services from "./components/Services";
  import About from "./components/About";
  import Footer from "./components/Footer";
  import Partners from "./components/Partners";
  import Team from "./components/Team";
  import Contact from "./components/Contact";
  export default {
    name: 'App',
    components: {
      Contact,
      Team,
      Partners,
      Footer,
      About,
      Services,
      MainScreen,
      Navbar,
      Courses
    }
  }
</script>

<style>
  #app {
  }
</style>
