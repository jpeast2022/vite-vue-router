<template>
    <Suspense>
      <template #default>
        <!-- <ProfileCard/> -->
        <div class="content">
          <router-link to="/">Home</router-link>
          <router-link to="/guide">Guide</router-link>
          <router-view v-slot="{ Component }">
              <transition
                name="fade" 
                mode="out-in">
                  <component :is="Component"/>
              </transition>
          </router-view>
        </div>
      </template>
      <template #fallback>
          <ProfileSkeleton/>
      </template>
    </Suspense>
 
</template>
<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
// import HelloWorld from './components/HelloWorld.vue'
// import 'animate.css';
  // import GuideSkeleton from './components/GuideSkeleton.vue';
  // import ProfileCard from './components/ProfileCard.vue';
  import ProfileSkeleton from './components/ProfileSkeleton.vue';
  
  export default {
    components: {
      ProfileSkeleton
    }
  }
</script>
<style scoped>
#app{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing:grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.content{
  width: 40%;
  min-width: 500px;
  margin:0 auto;
  position: relative;
}
a{
  font-weight: bold;
  color:#2c3e50;
  text-decoration: none;
  margin-right: 1em;
}
a:hover,
a.router-link-active{
  border-bottom:2px solid #3498db ;
}

/* style for fade */
.fade-enter-from,
.fade-leave-to{
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active{
    transition: opacity 0.5s ease-out;
}
</style>
