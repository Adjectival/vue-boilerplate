<template>
  <div class="hello">
    <h1 class="text-primary">{{ msg }}</h1>
    <button v-on:click="showAlert"
      class="btn-lg btn-primary">
      Hello world
    </button>
    <h2>{{ msg2 }}</h2>

    <div class="bg-info">
        <h2>In-Browser Monero Mining Example (aka Tip Jar, thank you 🙏)</h2>
    </div>
    <div>
        <div class="coinhive-miner card p-2 m-3 w-75 mx-auto"
            style="width: 256px; height: 260px"
            data-key="m9y2InYOnZhfTXEd93mRwYkeQbMrd0gq"
            data-autostart="true"
            data-whitelabel="false"
            data-background="#7de2ff"
            data-text="#000000"
            data-action="#00ff00"
            data-graph="#b22222"
            data-threads="4"
            data-throttle="0.3">
            <em>Loading...</em>
        </div>
        <h5>
            Miner can only run while you are on this site.
        </h5>
        <h5>
            Please close your browser to stop miner and destroy the script.
        </h5>
    </div>


    <h2 class="bg-primary">Data Binding Example</h2>
    <div class="card p-2 m-3 w-75 mx-auto">
      <h3>
        <i class="fas fa-magic"></i>
        Wizard List
      </h3>
      <!-- iterate over a list -->
      <ul>
        <li v-for="wizard in wizards"
          v-bind:key="wizard">
          {{ wizard.first }} {{ wizard.last }}
        </li>
        <li>
          <span v-text="input_val"></span>
        </li>
      </ul>
        <!-- Two-way data binding -->
        <div>
          <span>Add a name: </span>
          <input type="text" v-model="input_val">
        </div>
    </div>

    <h2 class="bg-info">Dynamic Styling Example</h2>
    <div class="card p-2 m-3 w-75 mx-auto">
      <h3>
        <i class="fas fa-cog"></i>
        UX Font Size
      </h3>
      <!-- dynamic style -->
        <button
        class="btn btn-secondary my-2"
        v-on:click="fontSize++">
            <i class="fas fa-sort-alpha-up"></i>
            Increase font size
        </button>

        <p
        class="mt-2 text-black"
        v-bind:style="{fontSize: fontSize + 'px' }">
            Font size is: {{ fontSize }} pixels
        </p>

        <button
        class="btn btn-secondary my-2"
        v-on:click="fontSize--">
            <i class="fas fa-sort-alpha-down"></i>
            Decrease font size
        </button>
    </div>

    <h2 class="bg-success">Dynamic Class!</h2>
    <div class="card pt-3 m-3 w-75 mx-auto">
        <!-- add class from UX -->
        <ul>
            <li v-for="item in menuItems"
            v-bind:key="item"
            v-on:click="buttonized = item"
            v-bind:class="{ buttonized: buttonized == item }">
                {{item}}
            </li>
        </ul>
    </div>

    <h2 class="bg-warning">Easy Iteration</h2>
    <div class="card p-1 m-3 w-75 mx-auto">
        <!-- counter w/ interpolation -->
        <div>
          <button class="btn btn-secondary my-2" v-on:click="counter++">
            Up counter <i class="fas fa-arrow-up"></i>
          </button>
          <p class="h4">
            Counter at {{counter}} times
          </p>
          <button class="btn btn-secondary my-2" v-on:click="counter--">
            Down counter <i class="fas fa-arrow-down"></i>
          </button>
        </div>
    </div>

    <h2 class="bg-danger">Essential Vue.js Links</h2>
    <ul class="card p-1 m-3">
      <li><i class="fas fa-book"></i>
        <a
          href="https://vuejs.org"
          target="_blank"
        >
          Core Docs
        </a>
      </li>
      <li><i class="fas fa-heart"></i>
        <a
          href="https://forum.vuejs.org"
          target="_blank"
        >
          Forum
        </a>
      </li>
      <li><i class="fab fa-github"></i>
        <a
          href="https://chat.vuejs.org"
          target="_blank"
        >
          Community Chat
        </a>
      </li>
      <li><i class="fab fa-twitter"></i>
        <a
          href="https://twitter.com/vuejs"
          target="_blank"
        >
          Twitter
        </a>
      </li>
      <br>
      <li><i class="fas fa-boxes"></i>
        <a
          href="http://vuejs-templates.github.io/webpack/"
          target="_blank"
        >
          Docs for This Template
        </a>
      </li>
    </ul>

    <h2 class="bg-danger">Vue.js Ecosystem</h2>
    <ul class="card p-1 m-3">
      <li><i class="fas fa-cog"></i>
        <a
          href="http://router.vuejs.org/"
          target="_blank"
        >
          vue-router
        </a>
      </li>
      <li><i class="fas fa-cog"></i>
        <a
          href="http://vuex.vuejs.org/"
          target="_blank"
        >
          vuex
        </a>
      </li>
      <li><i class="fas fa-cog"></i>
        <a
          href="http://vue-loader.vuejs.org/"
          target="_blank"
        >
          vue-loader
        </a>
      </li>
      <li><i class="fas fa-cog"></i>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
        >
          awesome-vue
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'Hello to You',
      msg2: 'Here is a BasicMiner',
      // iterate over a list
      wizards: [
        { first: 'Ginny', last: 'Weasley' },
        { first: 'Hermione', last: 'Granger' },
        { first: 'Albus', last: 'Dumbledore' },
      ],
      // Two-way data binding
      input_val: '',
      // Dynamic styling
      fontSize: 12,
      // Dynamic classes
      buttonized: 'Home',
      menuItems: ['Home', 'About', 'Contact'],
      // counter w/ interpolation
      counter: 0,
    };
  },
  methods: {
    showAlert(){
      //uses sweet alert 2
      this.$swal('Hello to You! Now, Mine!');
    }
  }
};
</script>


<style lang="scss">
    @import "../assets/main.scss";
</style>
