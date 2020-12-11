<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section title="About me">
        I am a Full Stack Web and Backend developer. I aim to become a subject
        matter expert in developing highly scalable, efficient, and fully-
        secure software systems with the best engineering practices.
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
        v-if="employments"
        title="Employment"
      >
        <v-layout
          v-for="(employment, i) in employments"
          :key="i"
        >
          <v-flex md4>
            {{ employment.from }} - {{ employment.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="employment.title">{{ employment.title }}</strong>
            <div v-if="employment.location">
              <i>{{ employment.location }}</i>
            </div>
            <div v-if="employment.description">
              {{ employment.description }}
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
          <template v-for="(skill, i) in skills">
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
              <div class="mr-3 ml-2">
                <div class="align-center">
                  <v-icon small>
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

      <content-section
        v-if="tools"
        id="to-timeline"
        title="Tools I am familiar with"
      >
        <v-layout wrap>
          <template
            v-for="(tool, i) in tools"
          >
            <v-flex

              :key="i"
              md4
              sm4
              xs12
            >
              <div
                class="mr-3 ml-3"
              >
                <div class="align-center">
                  <ul>
                    <li>{{ tool.text }}</li>
                  </ul>
                </div>
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>

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
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    employments: [
      {
        from       : '01/2019',
        to         : '12/2020',
        title      : 'Cybersecurity Researcher',
        location   : 'University of Regina, Regina, SK, Canada',
        description: '',
      },
      {
        from       : '11/2015',
        to         : '07/2018',
        title      : 'Software Development Engineer',
        location   : 'Tata Consultancy Services Ltd. (TCS), Ahmedabad, India',
        description: '',
      },
    ],
    educations: [
      {
        from : '2018',
        to   : '2020',
        title:
          'Master of Applied Science - Electronic Systems Engineering, GPA: 88.4/100',
        location: 'University of Regina, Regina, SK, Canada',
        // description: "",
      },
      {
        from    : '2011',
        to      : '2015',
        title   : 'Bachelor of Technology - Electrical Engineering, GPA: 3.46/4.0',
        location: 'Nirma University, Ahmedabad, India',
        // description: "",
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
        title: 'Spring Boot',
        icon : 'mdi-codepen',
        value: 70,
      },
      {
        title: 'React JS',
        icon : 'mdi-react',
        value: 50,
      },
      {
        title: 'MySQL / PostgreSQL',
        icon : 'mdi-database',
        value: 85,
      },
      {
        title: 'Zk',
        icon : 'mdi-code-braces',
        value: 82,
      },
      {
        title: 'Python',
        icon : 'mdi-language-python',
        value: 77,
      },
      {
        title: 'C++ / C',
        icon : 'mdi-language-c',
        value: 73,
      },
      {
        title: 'HTML5',
        icon : 'mdi-language-html5',
        value: 70,
      },
      // { divider: true },
      {
        title: 'CSS',
        icon : 'mdi-language-css3',
        value: 70,
      },
      {
        title: 'JUnit',
        icon : 'mdi-test-tube',
        value: 80,
      },
      {
        title: 'Distributed Systems',
        icon : 'mdi-server',
        value: 60,
      },
      {
        title: 'Linux',
        icon : 'mdi-linux',
        value: 55,
      },
      {
        title: 'Requirements Gathering',
        icon : 'mdi-text',
        value: 85,
      },
      {
        title: 'OO System Designs',
        icon : 'mdi-code-braces',
        value: 80,
      },
      {
        title: 'RDBMS Designs',
        icon : 'mdi-database-edit',
        value: 80,
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
        value: 90,
      },
      {
        title: 'Cybersecurity',
        icon : 'mdi-server-security',
        value: 70,
      },
      {
        title: 'Penetration Testing',
        icon : 'mdi-shield-lock',
        value: 70,
      },
      {
        title: 'Vulnerability Assessment',
        icon : 'mdi-security-network',
        value: 70,
      },
      {
        title: 'Machine Learning',
        icon : 'mdi-robot',
        value: 75,
      },
      // {
      //   title: 'C/C++',
      //   icon : 'mdi-language-cpp',
      //   value: 38,
      // },
      // { divider: true },
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
        icon  : '',
        text  : 'Eclipse',
        source: '',
      },
      {
        icon  : '',
        text  : 'Visual Studio Code',
        source: '',
      },
      {
        icon  : '',
        text  : 'SQuirrel SQL Client',
        source: '',
      },
      {
        icon  : '',
        text  : 'Jupyter Notebook',
        source: '',
      },
      {
        icon  : '',
        text  : 'Git',
        source: '',
      },
      {
        icon  : '',
        text  : 'Tortoise SVN',
        source: '',
      },
      {
        icon  : '',
        text  : 'Wireshark',
        source: '',
      },
      {
        icon  : '',
        text  : 'Riverbed Modeler',
        source: '',
      },
      {
        icon  : '',
        text  : 'Microsoft Visio',
        source: '',
      },
      {
        icon  : '',
        text  : 'Network Simulator (NS2)',
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
