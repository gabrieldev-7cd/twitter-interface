<template>
  <div id="app" class="flex container h-screen w-full">
    <div class="lg:w-1/5 border-r border-lighter border-indigo-800 lg:px-8 py-2 flex flex-col justify-between">
      <div>
        <button class="h-12 w-12 hover:bg-lightblue text-3xl rounded-full text-blue ">
          <i class="fab fa-twitter"></i>
        </button>
        <div>
          <button v-for="tab in tabs" :key="tab.id" @click="id = tab.id" class="focus:outline-none hover:text-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full mr-auto mb-3" v-bind:class=" id === tab.id ? 'text-blue' : ''" >
            <i class="text-2xl mr-4 text-left" v-bind:class="tab.icon"></i>
            <p class="text-lg font-semibold text-left hidden lg:block"> {{ tab.title }}</p>
          </button>
        </div>
        <button class="text-white bg-blue rounded-full font-semibold focus:outline-none w-12 h-12 lg:h-auto lg:w-full p-3 hover:bg-darkblue">
         <p class="hidden lg:block"> Tweet</p>
        </button>
      </div>
      <div class="lg:w-full relative">
        <button @click="dropdown = true" class="flex items-center w-full hover:bg-lightblue rounded-full p-3 focus:outline-none">
          <img src="@/assets/rayn_photo.jpg" class="w-10 h-10 rounded-full border border-lighter" />
          <div class="hidden lg:block">
            <p class="text-sm font-bold leading-tight">Ryan Dahl</p>
            <p class="text-sm leading-tight">@ryanmdahl</p>
          </div>
          <i class="fas fa-angle-down ml-auto text-lg"></i>
        </button>
        <div v-if="dropdown === true" class="absolute bottom-0 left-0 right-0 w-64 rounded-lg shadow-md border-lightest bg-white mb-16">
          <button @click="dropdown = false" class="p-3 flex items-center w-full hover:bg-lightest rounded-full p-3 focus:outline-none">
            <img src="@/assets/rayn_photo.jpg" class="w-10 h-10 rounded-full border border-lighter" />
            <div class="ml-4">
              <p class="text-sm font-bold leading-tight">Ryan Dahl</p>
              <p class="text-sm leading-tight">@ryanmdahl</p>
            </div>
            <i class="fas fa-check ml-auto text-blue"></i>
          </button>
          <button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 text-sm focus:outline-none">
            Adicionar conta existente
          </button>
           <button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 text-sm focus:outline-none">
            Log out @ryanmdahl
          </button>
        </div>
      </div>
    </div>
    <!-- tweets -->
    <div class="w-1/2 h-full">

    </div>
    <!-- trending -->
    <div class="w-1/3 h-full border-l border-lighter">

    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
    
  },
  data() {
    return {
      tabs:[
        {icon: 'fas fa-home', title: 'Home', id:'home'},
        {icon: 'fas fa-hashtag', title: 'Explore', id:'explore'},
        {icon: 'far fa-bell', title: 'Notifications', id:'notifications'},
        {icon: 'far fa-envelope', title: 'Messages', id:'messages'},
        {icon: 'far fa-bookmark', title: 'Bookmarks', id:'bookmarks'},
        {icon: 'fas fa-clipboard-list', title: 'Lists', id:'lists'},
        {icon: 'far fa-user', title: 'Profile', id:'lists'},
        {icon: 'fas fa-ellipsis-h', title: 'More', id:'lists'}
      ],
      id:'home',
      dropdown: false,
    }
  }
}
</script>

<style src="./assets/tailwind.css" />
