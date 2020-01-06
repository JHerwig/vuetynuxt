<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn v-for="(item, i) in items" :key="i" :href="item.to" link text>
        <v-icon left> {{ item.icon }} </v-icon> {{ item.title }}
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-dots-horizontal</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" height="1.5em">
      <v-row align-v="start">
        <v-col cols="6">
          <v-btn
            v-for="(item, i) in footerItems"
            :key="i"
            :href="item.to"
            link
            text
          >
            <v-icon left> {{ item.icon }} </v-icon> {{ item.title }}
          </v-btn>
        </v-col>
        <v-spacer />
        <v-col cols="auto" align-self="center">
          <span>&copy; 2019</span>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      footerItems: [
        {
          icon: 'mdi-apps',
          to: '/Impressum',
          title: 'Impressum'
        },
        {
          icon: 'mdi-apps',
          to: '/privacy_terms',
          title: 'Datenschutz'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Welcome!'
    }
  }
}
</script>
