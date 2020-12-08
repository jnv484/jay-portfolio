<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="About me"
      >
        I'm a web developer from India having close to 5 years of IT Industry experience.
        I'm interested and skilled in different topics of Information Technology including programming, web development.
      </content-section>
      <!-- <content-section
        v-if="prouds"
        title="What am I proud of?"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              <small>{{ proud.source }}</small>
            </p>
          </v-flex>
        </v-layout>
      </content-section> -->
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>

         <!-- <content-section
        v-if="tools"
        title="Tools I am familiar with!"
      >
        <v-layout
          v-for="(tool, i) in tools"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ tool.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ tool.text }}</strong><br>
              <small>{{ tool.source }}</small>
            </p>
          </v-flex>
        </v-layout>
      </content-section> -->
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    educations: [
      {
        from       : '2011',
        to         : '2015',
        title      : 'Bachelor\'s degree',
        location   : 'Shri Shankaracharya Institute, Raipur',
        description: '',
      },
      {
        from       : '2010',
        to         : '2011',
        title      : 'Intermediate',
        location   : 'Deshbandhu School, Raipur',
        description: '',
      },
      {
        from       : '2008',
        to         : '2009',
        title      : 'SSC',
        location   : 'CCHSS',
        description: '',
      },
    ],
    skills: [
      {
        title: 'Java',
        icon : 'mdi-language-java',
        value: 90,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 70,
      },
      {
        title: 'Python',
        icon : 'mdi-language-python',
        value: 70,
      },
      {
        title: 'React JS',
        icon : 'mdi-react',
        value: 40,
      },
      {
        title: 'Angular',
        icon : 'mdi-angular',
        value: 70,
      },
      {
        title: 'HTML',
        icon : 'mdi-language-html5',
        value: 70,
      },
      { divider: true },
      {
        title: 'CSS',
        icon : 'mdi-language-css3',
        value: 70,
      },
      {
        title: 'SQL-Server/PostgreSQL',
        icon : 'mdi-git',
        value: 70,
      },
      // {
      //   title: 'CentOS Server',
      //   icon : 'mdi-linux',
      //   value: 47,
      // },
      // {
      //   title: 'Web Application Security',
      //   icon : 'mdi-shield-lock',
      //   value: 80,
      // },
      // { divider: true },
      {
        title: 'Matlab',
        icon : 'mdi-chip',
        value: 29,
      },
      // {
      //   title: 'C/C++',
      //   icon : 'mdi-language-cpp',
      //   value: 38,
      // },
      { divider: true },
      // {
      //   title: 'Leadership',
      //   icon : 'mdi-account-group',
      //   value: 68,
      // },
      // {
      //   title: 'Content Marketing (+340 articles)',
      //   icon : 'mdi-text',
      //   value: 96,
      // },
    ],
    tools: [
      {
        icon: '',
        text: 'Postman',
        source: '',

      },
      {
        icon: '',
        text: 'Eclipse',
        source: '',

      },
      {
        icon: '',
        text: 'Jenkins',
        source: '',

      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
