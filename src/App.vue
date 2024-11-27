<template>
  <MainPage/>
  
</template>

<script>
import MainPage from './components/MainPage.vue';

export default {
  name: 'App',
  components: {
    MainPage
  },
  methods: {
  },
  data(){
    return {

    }
  },
  beforeMount(){
    if(localStorage.getItem('history') == null) localStorage.setItem('history', JSON.stringify([]))
  }
}
</script>

<style>
  @import url(./assets/bootstrap.css);
  
  #app{
    background-color: #082D33;
  }
  .auth, .reg{
    display: grid;
    place-items: center;
    height: 100dvh;
  }
  .form{
    width: 700px;
    height: fit-content;
    border-radius: 10px;
    background-color: #031617;
    padding: 30px 50px;
    color: white;
  }
  .form-floating{
    margin-bottom: 20px;
  }
  input::placeholder{
    color: #082D33;
  }
  a{
    cursor: pointer;
  }
</style>
