# vuejs-crash-course

# Create project using vue cli
sudo npm install -g @vue/cli
vue create my-project-name

# Compiles and hot-reloads for development
npm run serve

Now your project structure is ready to go.
Change your by default design.
Remove the Helloworld component from your template,
import statement and component name from component in export default from App.vue file.

# Add component
You can add component in your template.
Just create a vue file in component folder and import and add to your template.


Extention for VS code:
Vetur and vue

# Add css js or any kind of cdn/file
You can do it many way.
<style>
  @import './assets/styles/yourstyles.css';
</style>

Use NPM:
<script>
  require( 'datatables.net-dt' )();
  export default {
    name: 'Index',
    data() {
      return { 
      }
    }
  }
</script>

Or,
Add <script> tag to index.html
Just add the <script type="text/javascript" src="https://cdn.datatables.net/v/dt/dt-1.10.16/sl-1.2.5/datatables.min.js"></script> to the end of the index.html file, preferably right before </body>.

# Props
You can pass data to one component to another component.
<Nwe title="I am props"/>

<h1>{{title}}</h1>

You can define props in two way:
Like an array
Add it after component in export default.
props: ['title'],
Or can use in like json object
props: {
  title: String,
}

Also can add default value:
props: {
     title: {
         type: String,
         default: "Default value",
        }
    },

# Method in vue
we can use our event method.
<template>
    <button @click="clickme()">Click Me</button>
</template>

export default {
    name: "Nwe",
    components: {},
    props: ["title"],
    methods: {
        clickme() {
            console.log("Clicked!");
        },
    },
};

# State management and routing
Install the package for State management 
npm install --save vuex@next

Install the package for routing
npm i vue-router

Note: Vue Cli already install for you.

Manke a store folder and create a file called store.js
Add the following code...

import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

export const store = new Vuex.Store({
  //State
  state:{
    count: 0
  }
})

Now main.js file first we import our store.
import {store} from './store/store'
createApp(App).use(store).use(router).mount('#app')

Now you can access your state in your template.
{{$store.state.count}}

# How to use vue-router and Router Links
crete a file named routes.js in src folder
Then add the following code-
import About from './components/About.vue'
import Contact from './components/Contact.vue'

export default [
  { path:'/about', component:About },
  { path:'/contact', component:Contact }
]

Add the following code in main.js file
import {router} from './router'

createApp(App).use(store).use(router).mount('#app')

And finally add router view in your main App component.
<router-view></router-view>

Router Link:
Now you can link your router like that:
<router-link to="/about">About</router-link>

# Vuex
Some of vuex function:
<script>
import $ from 'jquery'
import {  mapGetters } from 'vuex';
import store from "../store";
export default {
  name: 'holderregistration',
  components: {
  },
  computed: mapGetters(['isLoggedIn']),
  methods: {
      register(){
          let username = $("#username").val();
          let email = $("#email").val();
          let password = $("#password").val();
          store.dispatch('finalizeLogin',{username, email, password})
          
          console.log(store.getters.isLoggedIn.email);
      }
  }
}
</script>

{{isLoggedIn}}

Note: Show in details in the following repo:
https://github.com/Apubra/vue-project



how to run script for specific component in vue?
Use mounted method.

Difference between the created and mounted events in Vue.js
created() : since the processing of the options is finished you have access to reactive data properties and change them if you want. At this stage DOM has not been mounted or added yet. So you cannot do any DOM manipulation here

mounted(): called after the DOM has been mounted or rendered. Here you have access to the DOM elements and DOM manipulation can be performed for example get the innerHTML:

console.log(element.innerHTML)
So your questions:

Is there any case where created would be used over mounted?
Created is generally used for fetching data from backend API and setting it to data properties. But in SSR mounted() hook is not present you need to perform tasks like fetching data in created hook only

What can I use the created event for, in real-life (real-code) situation?
For fetching any initial required data to be rendered(like JSON) from external API and assigning it to any reactive data properties

Example:
  created() {
      // $('#date').text(new Date().getFullYear())
    },
  mounted() {
      $('#date').text(new Date().getFullYear())
    },

Page not found routing:
{ path: '/:pathMatch(.*)*', component: PageNotFound }



# Component Structure
Sidebar(Menubar)
Navbar(Header)
Content(Body)
Footer


Note: We need separate all design in different components.
Otherwise we can reuse design.

Let's more practice...