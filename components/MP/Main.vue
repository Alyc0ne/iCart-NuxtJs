<template>
  <div>
    <div class="nav-sidebar">
      <!-- :style="{ left : paddingSidebar + 'px' }" -->
        <div class="nav-sidebar-inner-scroll">
            <ul class="sidebar-top-level-items">
                <li :class="{ navSidebarActive : this.$router.currentRoute.name === 'dashboard'}">
                    <!-- <img src="~/assets/icon-dashboard.png"> -->
                    <nuxt-link to="/Dashboard" :style="{ backgroundImage: 'url(' + require('@/assets/images/icon/icon-dashboard.png') + ')' }" class="icon-menu navSidebarActive"></nuxt-link>
                    <!-- <router-link to="/"><i class="fas fa-chart-line"><span class="LinkSidebar" :class="{ linkActive : this.$router.currentRoute.name === 'dashboard' }">Dashboard</span></i></router-link> -->
                </li>
                <li :class="{ navSidebarActive : this.$router.currentRoute.name === 'pos'}">
                  <nuxt-link to="/" :style="{ backgroundImage: 'url(' + require('@/assets/images/icon/icon-pos.png') + ')' }" class="icon-menu"></nuxt-link>
                </li>
                <li :class="{ navSidebarActive : this.$router.currentRoute.name === 'pos'}">
                  <nuxt-link to="/" :style="{ backgroundImage: 'url(' + require('@/assets/images/icon/icon-pos.png') + ')' }" class="icon-menu"></nuxt-link>
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
    <div class="content-wrapper">
      <!-- <nuxt-view></nuxt-view> -->

    </div>
  </div>
</template>
<script>

//Modal Control
// $(document).on('click', '#modal-btn', function () {
//   $('#my-modal').css('display','block')
// });
//Close Modal
// $(document).on('click', '.close, .closeModal', function () {
//   $('#my-modal').css('display','none')
// });

// export default {
//   name: 'leftmenu',
//   data () {
//     return {
//       isShowButton: false,
//       isSideBar: false,
//       paddingSidebar: '',
//       windowWidth: 0,
//       /*infoModal: {
//         Name: '',
//         isEdit: false
//       }*/
//     }
//   },
//   watch: {
//     windowWidth (newWidth) {
//       if (newWidth <= 768) {
//         this.paddingSidebar = -220
//       } else {
//         this.paddingSidebar = 0
//       }
//       this.isSideBar = false
//     }
//   },
//   mounted () {
//     this.$nextTick(() => {
//       window.addEventListener('resize', () => {
//         this.windowWidth = window.innerWidth
//       })
//     })
//   },
//   methods: {
//     openSideBar: function (e) {
//       if (e) {
//         this.paddingSidebar = 0
//         this.isSideBar = true
//       }
//     },
//     closeSideBar: function (e) {
//       if (e) {
//         this.paddingSidebar = -220
//         this.isSideBar = false
//       }
//     },
//     reLoadData: function (e) {
//       console.log('reLoadData Success !!')
//     },
//     newModal: function (e) {
//       var e = this.$store.dispatch('GenRunningNumber')
//       console.log(e)
//       // this.infoModal.Name = e
//       // this.infoModal.isEdit = false
//       // $('#my-modal').css('display','block')
//     },
//     editModal: function (e) {
//       //this.infoModal.Name = e.Name
//       //this.infoModal.isEdit = e.isEdit
//       $('#my-modal').css('display','block')
//       //this.isModalVisible = e
//     },
//     closeModal: function () {
//       $('#my-modal').css('display','none')
//     }
//     //,
//     // GenRunningNumber: function (action) {
//     //   this.$store.dispatch('GenRunningNumber')
//     // },
//     // SetSystemName: function (e) {
//     //   this.$store.dispatch('GenSystemName', e)
//     // }
//   }
// }
</script>
