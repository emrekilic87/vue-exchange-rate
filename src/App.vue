<template>
  <Exchange msg="US DOLLAR EXCHANGE RATES" :data="fetchDataArr" />
</template>

<script>
import Exchange from "./components/Exchange.vue";

export default {
  name: "App",
  components: {
    Exchange,
  },
  data() {
    return {
      fetchDataArr: {},
    };
  },
  methods: {
    fetchData() {
      fetch("https://open.exchangerate-api.com/v6/latest", {
        method: "GET",
      })
        .then((response) => response.json())
        .then((json) => (this.fetchDataArr = json));
    },
  },
  created() {
    this.fetchData();
  },
};
</script>

<style>
html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}
body {
  height: 100%;
  background-color: cadetblue;
  background: linear-gradient(284deg, #1ad72d, rgb(255, 4, 4));
  background-size: 400% 400%;
  -webkit-animation: AnimationName 9s ease infinite;
  -moz-animation: AnimationName 9s ease infinite;
  animation: AnimationName 9s ease infinite;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  height: 95%;
}

@-webkit-keyframes AnimationName {
  0% {
    background-position: 0% 41%;
  }
  50% {
    background-position: 100% 60%;
  }
  100% {
    background-position: 0% 41%;
  }
}
@-moz-keyframes AnimationName {
  0% {
    background-position: 0% 41%;
  }
  50% {
    background-position: 100% 60%;
  }
  100% {
    background-position: 0% 41%;
  }
}
@keyframes AnimationName {
  0% {
    background-position: 0% 41%;
  }
  50% {
    background-position: 100% 60%;
  }
  100% {
    background-position: 0% 41%;
  }
}
</style>
