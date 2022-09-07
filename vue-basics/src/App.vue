<template>
<div>
  <NavbarComponent/>
  <p class="text-center">2 + 2 = {{ 2 + 2 }}</p>
  <p class="text-center">{{greeting}}</p>
  <h1 class="text-center" v-if="!frameWorks">No FrameWorks</h1>
  <h1 class="text-center" v-else>FrameWorks!!!</h1>
  <div class="d-flex justify-content-center">
  <div class="card m-2" style="width: 18rem;" v-for="({title,description,content}, index) in frameWorks" :key="index">
  <div class="card-body">
    <h5 class="card-title">{{title}}</h5>
    <h6 class="card-subtitle mb-2 text-muted">{{description}}</h6>
    <p class="card-text">{{content}}</p>
  </div>
  </div>
</div>
  <FooterComponent/>
</div>
</template>

<script>
import NavbarComponent from "./components/NavbarComponent.vue"
import FooterComponent from "./components/FooterComponent.vue"
export default {
  name: "App",
  data(){
    return{
      greeting: String,
      frameWorks: [
        {
          title:"VUE",
          description: "Framework",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        },
        {
          title:"React",
          description: "Library",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        },
        {
          title:"Angular",
          description: "Framework",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        }
      ]
    }
  },
  components:{
    NavbarComponent,
    FooterComponent
  },
  methods:{
    sayHello(){
      this.greeting = "Hi!, I'm VUE"
    }
  },
  mounted(){
    this.sayHello()
  }
}
</script>