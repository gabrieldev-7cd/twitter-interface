<template>
  <div id="app" class="flex container h-screen w-full">
    <div class="w-1/5 border-r border-lighter border-indigo-800 px-8 py-2 flex flex-col justify-between">
      <div>
        <button class="h-12 w-12 hover:bg-lightblue text-3xl rounded-full text-blue ">
          <i class="fab fa-twitter"></i>
        </button>
        <div>
          <button v-for="tab in tabs" :key="tab.id" @click="id = tab.id" class="focus:outline-none hover:text-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full mr-auto mb-3" v-bind:class=" id === tab.id ? 'text-blue' : ''" >
            <i class="text-2xl mr-4 text-left" v-bind:class="tab.icon"></i>
            <p class="text-lg font-semibold text-left "> {{ tab.title }}</p>
          </button>
        </div>
        <button class="text-white bg-blue rounded-full font-semibold focus:outline-none w-full p-3 hover: bg-darkblue">
          Tweet
        </button>
      </div>
      <div class="w-full relative">
        <button class="flex items-center w-full hover:bg-lightblue rounded-full p-3 focus:outline-none">
          <img src="@/assets/rayn_photo.jpg" class="w-10 h-10 rounded-full border border-lighter" />
          <div class="ml-4">
            <p class="text-sm font-bold leading-tight">Ryan Dahl</p>
            <p class="text-sm leading-tight">@ryanmdahl</p>
          </div>
          <i class="fas fa-angle-down ml-auto text-lg"></i>
        </button>
        <div class="absolute left-0 bottom-0 right-0 w-64 rounded-lg shadow-md border-lightest bg-white mg-16">
          <button class="flex items-center w-full hover:bg-lightest rounded-full p-3 focus:outline-none">
            <img src="@/assets/rayn_photo.jpg" class="w-10 h-10 rounded-full border border-lighter" />
            <div class="ml-4">
              <p class="text-sm font-bold leading-tight">Ryan Dahl</p>
              <p class="text-sm leading-tight">@ryanmdahl</p>
            </div>
            <i class="fas fa-check ml-auto text-blue"></i>
          </button>
        </div>
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
      ],
      id:'home'
    }
  }
}
</script>

<style src="./assets/tailwind.css" />
