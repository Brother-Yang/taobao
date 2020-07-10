<template>
  <div style="height:100%;">
    <!-- <Details/> -->

    
      <keep-alive>
      <transition name="fadeMove">
        <router-view v-if="$route.meta.keepAlive" />
      </transition>
    </keep-alive>
    <keep-alive>
    <transition name="fadeMove">
      <router-view v-if="!$route.meta.keepAlive" />
    </transition>
    </keep-alive>
  </div>
</template>

<script>
// import Details from '@c/Details'
export default {
  data (){
    return {
     
    }
  },
  methods:{
  },
  components:{
    // Details
  }
}
</script>

<style lang="scss">
@import '@/styles/main';
</style>
