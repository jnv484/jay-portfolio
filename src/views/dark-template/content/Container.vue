<template>
  <v-card color="grey lighten-4" light>
    <v-card-text>
      <content-section title="About me">
        I am a Full Stack Web developer. I aim to become a subject matter expert
        in developing highly scalable, efficient, and fully- secure software
        systems with the best engineering practices.
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

      <content-section v-if="employments" title="Employment">
        <v-layout wrap>
          <template v-for="(employment, i) in employments">
            <v-flex v-if="!employment.divider" :key="i" md4 mb-4 xs12>
              <v-flex md6> {{ employment.from }} - {{ employment.to }} </v-flex>
              <v-flex md10>
                <strong v-if="employment.title">{{ employment.title }}</strong>
                <div v-if="employment.location">
                  <i>{{ employment.location }}</i>
                </div>
                <div v-if="employment.description">
                  {{ employment.description }}
                </div>
              </v-flex>
            </v-flex>

            <!-- <v-flex v-if="employment.divider" :key="i" md1 mb-4 xs12 /> -->
          </template>
        </v-layout>
      </content-section>

      <content-section v-if="skills" id="to-timeline" title="Skills">
        <template slot="actions"> (% are relative not absolute) </template>
        <v-layout wrap>
          <template v-for="(skill, i) in skills">
            <v-flex v-if="skill.divider" :key="i" md12 xs12 mb-4 />
            <v-flex v-else :key="i" md6 xs12>
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
          <template v-for="(tool, i) in tools">
            <v-flex :key="i" md4 sm4 xs6>
              <div class="mr-3 ml-3">
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

      <content-section v-if="educations" title="Education">
        <v-layout wrap>
          <template v-for="(education, i) in educations">
            <v-flex v-if="!education.divider" :key="i">
              <v-flex md6> {{ education.from }} - {{ education.to }} </v-flex>
              <v-flex md12>
                <strong v-if="education.title">{{ education.title }}</strong>
                <div v-if="education.location">
                  <i>{{ education.location }}</i>
                </div>
                <div v-if="education.description">
                  {{ education.description }}
                </div>
              </v-flex>
            </v-flex>
            <v-flex v-if="education.divider" :key="i" md12 xs12 mb-4 />
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from "@/views/dark-template/content/Section";
export default {
  name: "MainContent",
  components: { ContentSection },
  data: () => ({
    employments: [
    {
        from: "02/2021",
        to: "present",
        title: "Research Analyst",
        location: "British Columbia Institute of Technology",
        description: "Burnaby, BC, Canada",
      },
      {
        from: "01/2019",
        to: "12/2020",
        title: "Cybersecurity Researcher",
        location: "University of Regina",
        description: "Regina, SK, Canada",
      },
      { divider: true },
      {
        from: "11/2015",
        to: "07/2018",
        title: "Software Development Engineer",
        location: "Tata Consultancy Services Ltd. (TCS)",
        description: " Ahmedabad, India",
      },
    ],
    educations: [
      {
        from: "2018",
        to: "2020",
        title:
          "Master of Applied Science - Electronic Systems Engineering, GPA: 4.0/4.0",
        location: "University of Regina, Regina, SK, Canada",
        // description: "",
      },
      { divider: true },
      {
        from: "2011",
        to: "2015",
        title: "Bachelor of Technology - Electrical Engineering, GPA: 3.46/4.0",
        location: "Nirma University, Ahmedabad, India",
        // description: "",
      },
      { divider: true },
    ],
    skills: [
    {
        title: "JavaScript",
        icon: "mdi-language-javascript",
        value: 95,
      },
      {
        title: "React JS",
        icon: "mdi-react",
        value: 95,
      },
      {
        title: "Node JS",
        icon: "mdi-nodejs",
        value: 87,
      },
      {
        title: "Python",
        icon: "mdi-language-python",
        value: 90,
      },
      {
        title: "Django",
        icon: "mdi-codepen",
        value: 90,
      },
      {
        title: "Java",
        icon: "mdi-language-java",
        value: 95,
      },
      {
        title: "Spring Boot",
        icon: "mdi-codepen",
        value: 70,
      },
      {
        title: "JUnit",
        icon: "mdi-test-tube",
        value: 80,
      },
      {
        title: "HTML5",
        icon: "mdi-language-html5",
        value: 99,
      },
      {
        title: "CSS",
        icon: "mdi-language-css3",
        value: 99,
      },
      {
        title: "MySQL / PostgreSQL",
        icon: "mdi-database",
        value: 85,
      },
      {
        title: "Git",
        icon: "mdi-git",
        value: 95,
      },
      {
        title: "Docker",
        icon: "mdi-docker",
        value: 85,
      },
      {
        title: "Amazon Web Services (AWS)",
        icon: "mdi-aws",
        value: 70,
      },
      {
        title: "Linux",
        icon: "mdi-linux",
        value: 80,
      },
      {
        title: "Requirements Gathering",
        icon: "mdi-text",
        value: 85,
      },
      {
        title: "OO System Designs",
        icon: "mdi-code-braces",
        value: 80,
      },
      {
        title: "RDBMS Designs",
        icon: "mdi-database-edit",
        value: 80,
      },
      {
        title: "Cybersecurity",
        icon: "mdi-server-security",
        value: 70,
      },
      {
        title: "Machine Learning",
        icon: "mdi-robot",
        value: 75,
      },
    ],
    tools: [
    {
        icon: "",
        text: "Git",
        source: "",
      },
    {
        icon: "",
        text: "Node Package Manager (npm)",
        source: "",
      },
      {
        icon: "",
        text: "pip",
        source: "",
      },
    {
        icon: "",
        text: "Visual Studio Code",
        source: "",
      },
      {
        icon: "",
        text: "PyCharm",
        source: "",
      },
      {
        icon: "",
        text: "Eclipse",
        source: "",
      },
      {
        icon: "",
        text: "MySQL Workbench",
        source: "",
      },
      {
        icon: "",
        text: "Jupyter Notebook",
        source: "",
      },
      {
        icon: "",
        text: "Putty",
        source: "",
      },
      {
        icon: "",
        text: "Wireshark",
        source: "",
      },
    ],
  }),
};
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
