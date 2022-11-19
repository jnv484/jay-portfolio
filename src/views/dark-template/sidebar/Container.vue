<template>
  <v-card color="grey darken-3" dark>
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          <!-- Jay <span class="light-blue--text text--lighten-3">Nayak</span> -->
          <span class="light-blue--text text--lighten-2">Jay Nayak, MASc</span>
        </h1>
        <span> Software Engineer </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.interests">
        <template v-slot:item="{ item }">
          <v-chip>
            <!-- <v-avatar> -->
            <!-- <v-icon>
                {{ item.icon }}
              </v-icon> -->
            <!-- </v-avatar> -->
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>

      <sidebar-section :options="sections.additional" />
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{ items }">
          <v-container pa-0>
            <v-layout wrap class="text-xs-center">
              <template v-for="(item, i) in items">
                <v-flex :key="i" md4 sm4 xs6>
                  <v-progress-circular
                    rotate="360"
                    size="100"
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
import Avatar from "@/views/dark-template/sidebar/Avatar";
import SidebarSection from "@/views/dark-template/sidebar/Section";
export default {
  name: "Sidebar",
  components: { SidebarSection, Avatar },
  data() {
    return {
      sections: {
        info: {
          title: "INFO",
          items: [
            {
              name: "Email",
              icon: "mdi-email",
              text: "jayknayak@gmail.com",
            },
            // {
            //   name: "Contact Number",
            //   icon: "mdi-cellphone",
            //   text: "+1 639-999-6561",
            // },
            // {
            //   name: "Website",
            //   icon: "mdi-web",
            //   text: "jayknayak.com",
            // },
            {
              name: "Resume",
              icon: "mdi-text",
              file: "Resume_JayNayak.docx",
              text: "Save My Resume",
            },
            // {
            //   name: "Address",
            //   icon: "mdi-map-marker",
            //   text: "16 – 4239 Degeer St, Saskatoon, SK, S7H 4N6",
            // },
          ],
        },
        socials: {
          title: "SOCIALS",
          items: [
            //  {
            //    icon: "mdi-github-circle",
            //    text: "github.com/Jay-a",
            //    link: "https://github.com/Jay-a",
            //  },
            {
              icon: "mdi-linkedin-box",
              text: "linkedin.com/in/JayNayak",
              link: "https://www.linkedin.com/in/jayknayak/",
            },
            {
              icon: "mdi-github-box",
              text: "github.com/jayknayak",
              link: "https://github.com/jayknayak",
            },
            {
              icon: "mdi-twitter",
              text: "twitter.com/JayNayak",
              link: "https://twitter.com/jayknayak",
            },
            // {
            //   icon: "mdi-instagram",
            //   text: "instagram.com/JayNayak",
            //   link: "https://instagram.com/jayknayak",
            // },
          ],
        },
        interests: {
          title: "INTERESTS",
          items: [
            {
              icon: "mdi-auto-fix",
              text: "Programming",
            },
            {
              icon: "mdi-auto-fix",
              text: "Cybersecurity",
            },
            {
              icon: "mdi-auto-fix",
              text: "Aritificial Intelligence (AI)",
            },
            {
              icon: "mdi-auto-fix",
              text: "Cosmos",
            },
            {
              icon: "mdi-auto-fix",
              text: "Continuous Self-development",
            },
            // {
            //   icon: 'mdi-biohazard',
            //   text: 'Challenges',
            // },
            // {
            // icon: "mdi-bike",
            // text: "Cycling",
            // },
            // {
            //   icon: 'mdi-image-filter-hdr',
            //   text: 'Nature',
            // },
            // {
            //   icon: 'mdi-auto-fix',
            //   text: 'Hacking Stuffs',
            // },
            // {
            // icon: "mdi-teach",
            // text: "Teaching",
            // },
            // {
            //   icon: 'mdi-karate',
            //   text: 'Sports',
            // },
            // {
            // icon: "mdi-music",
            // text: "Music",
            // },
            // {
            //   icon: 'mdi-account-group',
            //   text: 'Leadership',
            // },
            // {
            // icon: "mdi-book-open-page-variant",
            // text: "Books",
            // },
            // {
            //  icon: "mdi-android-debug-bridge",
            //  text: "Tickling Bugs!",
            // },
          ],
        },

        additional: {
          title: "ACCOLADES",
          type: "awards",
          items: [
            // { text: 'Mentoring junior software engineers in TCS, India.' },
            {
              text:
                "‘On The Spot Award’ (Award for Excellence) in TCS for successfully developing a project in a very crucial deadline.",
            },
            // { text: 'Graduate Teaching Assistant at University of Regina, SK, Canada (2019 – 2020).' },
            {
              text:
                "The Saskatchewan Innovation and Excellence Graduate Scholarship, SK, Canada (twice).",
            },
            { text: "Master’s Award, University of Regina, SK, Canada." },
          ],
        },
        languages: {
          title: "LANGUAGES",
          items: [
            {
              text: "English",
              value: 95,
            },
            {
              text: "Hindi",
              value: 100,
            },
            {
              text: "Gujarati",
              value: 100,
            },
          ],
        },
      },
    };
  },
};
</script>

<style scoped>
.sidebar {
  background: #2e2e2e;
}
</style>
