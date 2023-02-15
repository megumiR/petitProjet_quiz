<template>
  <div id="app">
    <header class="site">
      <nav class="site-nav">
        <div class="flexbox">
          <h1>QUIZ APP</h1>
        </div>
        <div class="flexbox">
          <button @click="openTogglemenu">
            <font-awesome-icon icon="fa-solid fa-bars" />
          </button>
          <div class="flexbox site-nav-links" v-if="!isOpen">
            <router-link to="/" class="site--nav__link">Home</router-link>
            <router-link to="/add" class="site--nav__link"
              >Add quiz</router-link
            >
            <router-link to="/login" class="site--nav__link">Login</router-link>
          </div>
        </div>
      </nav>
    </header>
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      //userId: localStorage.getItem("userID"),
      isOpen: false,
    };
  },
  //mounted() {this.getQuiz();},
  methods: {
    openTogglemenu: () => {
      this.isOpen = this.isOpen ? false : true;
    },
  },
};
</script>

<style lang="scss">
$color-primary: #ff193c;
$color-secondary: #ff9299;
$color-tertiary: #ebdcff;

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.site {
  background-color: $color-secondary;
  display: flex;
  flex-direction: column;
  min-height: 3em;
  padding: 1rem;
}
.site-nav {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.flexbox {
  display: flex;
  justify-content: flex-start;
}
.site-nav__link {
  padding-right: 0.5rem;
  font-weight: bold;
  text-decoration: none;
  &:hover {
    background-color: #ff193c;
    opacity: 0.8;
    transform: scale(1.2);
  }
}
@media only screen and (max-width: 768px) {
  .flexbox {
    flex-direction: column;
  }
  .site-nav-links {
    display: none;
  }
  .site-nav__link {
    margin-left: 0;
  }
  .site-nav-link__toggle {
    align-self: flex-end;
    cursor: pointer;
  }
}
</style>
