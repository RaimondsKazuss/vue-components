<template>
    <Header/>
    <div class="page-container">
      <Article
      v-for="article in articleArray"
      :title="article.title"
      :img="article.img"
      :key="article.title"
      v-on:click="clicker"
      />
    </div>
    <Login :authType="authType" />
</template>

<script>
import Header from './components/Header.vue'
import Article from './components/Article.vue'
import Login from './components/Login.vue'

export default {
  name: 'App',
  data () {
    return {
      articleArray: [
        {
          title: "White duck steals bread",
          img: "https://images.unsplash.com/photo-1597840637868-417c13c7e962?ixid=MnwxMjA3fDB8MHxzZWFyY2h8Nnx8ZHVja3xlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&w=1000&q=80"
        },
        {
          title: "Record fast duck swimming",
          img: "https://upload.wikimedia.org/wikipedia/commons/a/a1/Mallard2.jpg"
        },
        {
          title: "The most beatuful duck in the world",
          img: "https://nas-national-prod.s3.amazonaws.com/styles/hero_mobile/s3/nyc-mandarin-duck_holly-mascaro.jpg?itok=-UKJAxBT"
        }
      ],
      authType: "/register"
    }
  },
  components: {
    Header,
    Article,
    Login
  },
  methods: {
    clicker () {
      console.log('clickerino works!')
    },
    submitFn () {
      console.log('logged in!')
    },
    authSwitcher () {
    const navUrl = "/register";

    if (navUrl === "/register") {
      return this.authType = {
        title: "Login",
        callBack: this.submitFn
      }
    }
}
  },
  mounted() {
    this.authSwitcher()
  }
}
</script>


//concept



<style>
  body {
    margin: 0;
    padding: 0;
    width: 100%;
    color: #222;
    font-family: Open-sans, sans-serif;
  }

  .page-container {
    max-width: 60rem;
    height: 100%;
    display: flex;
    flex-direction: row;
    margin: auto;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 0;
  }

  @media (max-width: 768px) {
    .page-container {
      flex-direction: column;
      align-items: center; 
    }
  }
</style>
