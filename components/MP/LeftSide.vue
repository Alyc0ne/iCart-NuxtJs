<template>
  <div>
    <div class="nav-sidebar">
      <!-- :style="{ left : paddingSidebar + 'px' }" -->
        <div class="nav-sidebar-inner-scroll">
            <ul class="sidebar-top-level-items">
                <li>
                    <nuxt-link to="/" :style="{ backgroundImage: 'url(' + require('@/assets/images/icon/icon-dashboard.png') + ')' }" class="icon-menu" :class="{ navSidebarActive : $nuxt.$route.name === 'index'}"></nuxt-link>
                </li>
                <li>
                  <nuxt-link to="/pos" :style="{ backgroundImage: 'url(' + require('@/assets/images/icon/icon-pos.png') + ')' }" class="icon-menu" :class="{ navSidebarActive : $nuxt.$route.name === 'pos'}"></nuxt-link>
                </li>
                <!-- <li>
                    <router-link to="dashboard/1">Unit</router-link>
                </li> -->
                <!-- <li :class="{ navSidebarActive : this.$router.currentRoute.name === 'Goods'}">
                    <router-link to="Goods"><i class="fas fa-cubes"><span class="LinkSidebar">Goods</span></i></router-link>
                </li>
                <li :class="{ navSidebarActive : this.$router.currentRoute.name === 'teststate'}">
                    <router-link to="teststate"><i class="fas fa-cubes"><span class="LinkSidebar">ttt</span></i></router-link>
                </li> -->
            </ul>
        </div>
    </div>
  </div>
</template>
<script>
export default {
    data () {
        this.Get()
        return {
            
        }
    },
    methods: {
        Get: function () {
            console.log(this.$router.currentRoute.name);
        }
    }
}
</script>
