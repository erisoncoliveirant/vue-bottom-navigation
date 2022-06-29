<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
    <WindowsBottomNavigation :options="options" v-model="selected">
      <template #icon="{ props }">
        <v-icon
          :color="props.color"
        >
          {{ props.icon }}
        </v-icon>
      </template>
    </WindowsBottomNavigation>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
    WindowsBottomNavigation: () => import('@/components/WindowsBottomNavigation.vue')
  },

  data: () => ({
    selected: null,
    options: [
      {
        id: 'home',
        path: {
          name: 'home'
        },
        icon: 'mdi-microsoft-windows',
        color: '#1FABFF'
      },
      {
        id: 'about',
        path: {
          name: 'about'
        },
        icon: 'mdi-folder',
        color: '#FFD65A'
      },
      { id: 3, icon: 'mdi-discord', color: '#5662F6' },
      { id: 4, icon: 'mdi-phone', color: '#1784c5', badge: 4 },
      { id: 5, icon: 'mdi-spotify', color: '#1ED760' }
    ]
  })
}
</script>
