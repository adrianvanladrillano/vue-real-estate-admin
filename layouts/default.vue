<template>
  <div>
    <div class="tile is-ancestor is-gapless">
      <div
        class="column is-2 is-parent"
        style="
          height: 100vh;
          background: #FFFFFF;
          border-right: 1px solid #f4f6f8;
        "
      >
        <div class="columns">
          <div class="column" style="padding: 50px">
            <img src="https://bulma.io/images/bulma-logo.png" alt="" />
          </div>
        </div>

        <div class="columns">
          <div class="column sidebar">
            <NuxtLink
              :to="item.route"
              class="my-3 sidenav"
              style="font-weight: 500"
              v-for="item in items"
              :key="item.title"
            >
              <span class="icon-text">
                <span class="icon">
                  <i :class="item.icon"></i>
                </span>
                <span class="ml-3">{{ item.title }}</span>
              </span>
            </NuxtLink>
          </div>
        </div>
      </div>
      <div class="column is-10" style="background: white">
        <div class="container-fluid">
          <nuxt class="is-fullheight" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'Dashboard',
          icon: 'mdi mdi-24px	 mdi-home-variant-outline mr-5',
          route: '/',
        },
        {
          title: 'Listings',
          icon: 'mdi mdi-24px	 mdi-domain mr-5',
          route: '/Listings',
        },
        {
          title: 'Developers',
          icon: 'mdi mdi-24px	 mdi-cog-outline mr-5',
          route: '/Developers',
        },
        {
          title: 'Projects',
          icon: 'mdi mdi-24px	 mdi-cog-outline mr-5',
          route: '/Projects',
        },
        {
          title: 'Appointments',
          icon: 'mdi mdi-24px	 mdi-calendar mr-5',
          route: '/Appointments',
        },
        {
          title: 'Inquiries',
          icon: 'mdi mdi-24px	 mdi-message-settings-outline mr-5',
          route: '/Inquiries',
        },
        {
          title: 'Settings',
          icon: 'mdi mdi-24px	 mdi-cog-outline mr-5',
          route: '/Settings',
        },
      ],
    }
  },
  mounted() {
    console.log(this.$route.path)
  },
}
</script>
<style>
.sidebar {
  margin: 0;
  padding: 0;
}
.mapouter {
}
.gmap_canvas {
}
a.sidenav {
  display: block;
  color: gray;
  padding: 16px;
  letter-spacing: 1px;
  text-decoration: none;
  margin-left: 2.5em;
  margin-right: auto;
}

a.sidenav.active {
  background-color: white;
  color: white;
}

.sidebar a:hover {
  background-color: white;
  color: black;
  border-right: 5px solid #00d1b2;
  font-weight: 700;
}
</style>
