<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Sashin <span class="light-blue--text text--lighten-3">Agrawal</span>
        </h1>
        <span>
         Full stack Web developer
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  :key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'sashin.agrawal1@gmail.com',
            },
            {
              name: 'Contact Number',
              icon: 'mdi-cellphone',
              text: '+91-7984005427',
            },
            {
              name: 'Website',
              icon: 'mdi-web',
              text: 'sashinagrawal.in',
            },
            {
              name: 'Birth Date',
              icon: 'mdi-cake-variant',
              text: 'Jul 16, 1993',
            },
            {
              name: 'Nationality',
              icon: 'mdi-map-marker',
              text: 'Hyderabad, India',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/Sashin-a',
              link: 'https://github.com/Sashin-a',
            },
            {
              icon: 'mdi-linkedin-box',
              text: 'linkedin.com/in/sashin-agrawal',
              link: 'https://linkedin.com/in/sashin-agrawal',
            },
            // {
            //   icon: 'mdi-twitter',
            //   text: 'twitter.com/Sashin Agrawal',
            //   link: 'https://twitter.com/imSashin',
            // },
            {
              icon: 'mdi-instagram',
              text: 'instagram.com/sashinagrawal',
              link: 'https://www.instagram.com/sashinagrawal/',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [

            // {
            //   icon: 'mdi-bullseye',
            //   text: 'Getting out of Safe Zone',
            // },
            // {
            //   icon: 'mdi-biohazard',
            //   text: 'Challenges',
            // },
            {
              icon: 'mdi-bike',
              text: 'Cycling',
            },
            // {
            //   icon: 'mdi-image-filter-hdr',
            //   text: 'Nature',
            // },
            // {
            //   icon: 'mdi-auto-fix',
            //   text: 'Hacking Stuffs',
            // },
            {
              icon: 'mdi-teach',
              text: 'Teaching',
            },
            // {
            //   icon: 'mdi-karate',
            //   text: 'Sports',
            // },
            {
              icon: 'mdi-music',
              text: 'Music',
            },
            // {
            //   icon: 'mdi-account-group',
            //   text: 'Leadership',
            // },
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Books',
            },
            {
              icon: 'mdi-android-debug-bridge',
              text: 'Tickling Bugs!',
            },
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            
            {
              text : 'Hindi',
              value: 100,
            },
            {
              text : 'English',
              value: 90,
            },
            
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
