<template>
  <div id="app" class="flex container h-screen w-full">
    <div class="w-1/5 border-r border-lighter border-indigo-800 px-8 py-2 ">
      <button class="h-12 w-12 hover:bg-lightblue text-3xl rounded-full text-blue ">
        <i class="fab fa-twitter"></i>
      </button>
      <div>
        <button v-for="tab in tabs" :key="tab.id" class="hover:tex-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full mr-auto">
          <i :class=" '${ tab.icon } text-2xl mr-4 ' "></i>
          <p class="text-lg font-semibold text-left "> {{ tab.title }}</p>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
      return {
        tabs:[
          {icon: 'fas fa-home', title: 'Home', id:'home'},
          {icon: 'fas fa-hashtag', title: 'Explore', id:'explore'},
          {icon: 'fas fa-bell', title: 'Notifications', id:'notifications'},
          {icon: 'fas fa-envelope', title: 'Messages', id:'messages'},
          {icon: 'fas fa-bookmark', title: 'Bookmarks', id:'bookmarks'},
          {icon: 'fas fa-clipboard-list', title: 'Lists', id:'lists'},
        ]
      }
  }
}
</script>

<style src="./assets/tailwind.css" />
