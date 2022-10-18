<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1 class="title is-1" v-text="form.formName"></h1>

    <div class="columns">
      <div class="column">
        <form name="form" id="form" v-on:submit.prevent="Save()">
          <p>
            ID:
            <input
              type="text"
              name="id"
              placeholder="Ingrese id"
              class="form-control"
              v-model="form.idNumber"
            />
          </p>
          <p>
            Name:
            <input
              type="text"
              name="name"
              placeholder="Ingrese name"
              class="form-control"
              v-model="form.name"
            />
          </p>
          <hr />
          <input
            class="button is-primary margin-bottom"
            type="submit"
            @click.prevent="Save()"
          />
        </form>

        <transition name="fade" mode="out-in">
          <article class="message is-primary" v-show="showSubmitFeedback">
            <div class="message-header">
              <!-- <p>Fake Send Status:</p> -->
            </div>
            <div class="message-body">Successfully Submitted!</div>
          </article>
        </transition>
      </div>
      <div class="column">
        <h5>JSON</h5>
        <pre><code>{{form}}</code></pre>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: "App",
  data() {
    return {
      form: {
        formName: "Formulario",
        idNumber: "",
        name: "",
      },
      showSubmitFeedback: false,
    };
  },
  methods: {
    async Save() {
      console.log(this.idNumber);
      console.log(this.name);

      /////////////////////////////
      // var myHeaders = new Headers();
      // myHeaders.append("Content-Type", "application/json");

      // const raw = JSON.stringify(this.form);
      // console.log(raw);

      // var r = {
      //   mode: "no-cors",
      //   method: "POST",
      //   headers: {
      //     "Content-type": "application/json",
      //     "Access-Control-Allow-Origin": "*",
      //   },
      //   body: raw,
      // };
      // console.log(r);
      // fetch("http://localhost:3000/posts/nosql", r)
      //   .then((response) => response.json())
      //   .then((result) => console.log(result))
      //   .catch((error) => console.log("error", error));
      // this.showSubmitFeedback = true;
      // setTimeout(() => {
      //   this.showSubmitFeedback = false;
      // }, 3000);
    },
  },
  components: {
    // HelloWorld
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
.margin-bottom {
  margin-bottom: 15px;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
</style>
