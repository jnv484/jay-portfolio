<template>
  <v-card color="grey lighten-4" light>
    <v-card-text>
      <content-section
        id="timeline"
        :title="detailed ? 'Academic Works' : 'My Experiences'"
      >
        <template slot="actions">
          <div>
            <v-switch
              v-model="detailed"
              class="mr-4"
              :label="detailed ? 'Go back' : 'Switch to Academics'"
            />
          </div>
        </template>

        <v-timeline v-if="!detailed" dense>
          <v-timeline-item
            v-for="(item, i) in orderedItems"
            :key="i"
            :icon="item.icon || ''"
            :class="{ transparent: item.transparent }"
            large
          >
            <template v-if="item.iconImage" v-slot:icon>
              <v-avatar>
                <img :src="publicPath(item.iconImage)" />
              </v-avatar>
            </template>
            <template v-slot:opposite />
            <v-layout>
              <v-flex
                v-if="$vuetify.breakpoint.smAndUp"
                md1
                sm2
                align-self-center
              >
                <span>{{ item.year }}</span>
              </v-flex>
              <v-flex md11 sm10 xs12>
                <v-card class="elevation-1">
                  <v-card-title class="pb-0">
                    <div>
                      <p v-if="$vuetify.breakpoint.xsOnly">
                        {{ item.year }}
                      </p>
                      <h3>{{ item.title }}</h3>
                    </div>
                  </v-card-title>
                  <v-card-text>
                    <v-layout wrap>
                      <v-flex :md7="!!item.image" :md12="!item.image" xs12>
                        <div class="mr-1">
                          <span v-if="item.text" class="pre">{{
                            item.text
                          }}</span>
                          <!-- eslint-disable vue/no-v-html -->
                          <div v-else-if="item.html" v-html="item.html" />
                          <!-- eslint-enable vue/no-v-html -->
                        </div>
                      </v-flex>
                      <v-flex v-if="item.image" md5 xs12>
                        <div class="mt-2">
                          <v-carousel
                            v-if="Array.isArray(item.image)"
                            :show-arrows="false"
                            :height="325"
                          >
                            <v-carousel-item
                              v-for="(citem, ci) in item.image"
                              :key="ci"
                              :src="publicPath(citem)"
                            />
                          </v-carousel>
                          <v-img
                            v-else
                            :max-height="
                              item.imageHeight ? item.imageHeight : ''
                            "
                            :src="publicPath(item.image)"
                          />
                        </div>
                      </v-flex>
                    </v-layout>
                  </v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
        <template v-if="detailed">
          <v-layout style="margin-bottom: 2em">
            <v-flex md12 sm10 xs12>
              <v-card class="elevation-1">
                <v-card-title class="pb-0">
                  <div>
                    <h3>Research and Projects (Academic)</h3>
                  </div>
                </v-card-title>
                <v-card-text>
                  <v-layout column>
                    <!-- <v-flex :md7="!!item.image" :md12="!item.image" xs12> -->
                    <div class="mr-1">
                      <span
                        ><ul
                          style="list-style-type: disc; word-wrap: break-word"
                        >
                          <li>
                            Developed cyber security architectures for critical
                            infrastructure systems to analyze security
                            vulnerabilities, secure operations, and secure
                            siting of distributed generation (such as, Small
                            Modular Reactors (SMRs)).
                          </li>
                          <li>
                            Designed enterprise network architecture using
                            communication protocols (such as, TCP/IP, UDP,
                            IPSEC, SSL/TLS, routing protocols) to create
                            geographically separated and interconnected
                            autonomous systems.
                          </li>
                          <li>
                            Developed a health care monitoring system with
                            wireless sensor network in the lab!
                          </li>
                          <li>
                            Modeled a sentiment analysis / information retrieval
                            of movie reviews using Natural Language Processing
                            (NLP) and Machine Learning algorithms in Python.
                          </li>
                          <li>
                            Developed a reverse blocking (RB) application
                            between two relaying systems for a coordinated
                            protection scheme in the lab.
                          </li>
                          <li>
                            Developed an energy management system in the lab to
                            regulate the energy flow between power stations and
                            substations.
                          </li>
                        </ul></span
                      >
                    </div>
                    <!-- </v-flex> -->
                  </v-layout>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>

          <v-layout style="margin-bottom: 2em">
            <v-flex md12 sm10 xs12>
              <v-card class="elevation-1">
                <v-card-title class="pb-0">
                  <div>
                    <h3>List of Publications/Presentations</h3>
                  </div>
                </v-card-title>
                <v-card-text>
                  <v-layout column>
                    <!-- <v-flex :md7="!!item.image" :md12="!item.image" xs12> -->
                    <div class="mr-1">
                      <span
                        ><ul
                          style="list-style-type: disc; word-wrap: break-word"
                        >
                        
                        <li>
                          Nayak, J., Al-Anbagi, I.:
Vulnerability assessment and defence strategy to site
distributed generation in smart grid. IET Smart Grid.
1–16 (2022). https://doi.org/10.1049/stg2.12059
                          </li>
                          <li>
                            J. Nayak and I. Al-Anbagi, "Modelling False Data
                            Injection Attacks Against Non-linear State
                            Estimation in AC Power Systems," 2020 8th
                            International Conference on Smart Grid (icSmartGrid)
                            , Paris, France, 2020, pp. 37-42, doi:
                            10.1109/icSmartGrid49881.2020.9144947.
                          </li>
                          <li>
                            J. Nayak and I. Al-Anbagi, "The Impact of Cybersecurity on Siting Distributed Generation Units in AC Power Systems," 2020 IEEE Electric Power and Energy Conference (EPEC), 2020, pp. 1-6, doi: 10.1109/EPEC48502.2020.9319924.
                          </li>
                        </ul></span
                      >
                    </div>
                    <!-- </v-flex> -->
                  </v-layout>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>

          <v-layout style="margin-bottom: 2em">
            <v-flex md12 sm10 xs12>
              <v-card class="elevation-1">
                <v-card-title class="pb-0">
                  <div>
                    <h3>Thesis</h3>
                  </div>
                </v-card-title>
                <v-card-text>
                  <v-layout column>
                    <!-- <v-flex :md7="!!item.image" :md12="!item.image" xs12> -->
                    <div class="mr-1">
                      <span
                        >Jay Nayak, Cybersecurity Impact on Siting Distributed
                        Generation in a Smart Grid Environment, Master of
                        Applied Science, Electronic Systems Engineering,
                        University of Regina, October 2020.</span
                      >
                    </div>
                    <!-- </v-flex> -->
                  </v-layout>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </template>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from "@/views/dark-template/content/Section";
export default {
  name: "Timeline",
  components: { ContentSection },
  data: () => ({
    detailed: false,
    items: [
      {
        detailed: true,
        transparent: true,
        year: "1993",
        title: "Born on July 16, 1993",
        html:
          "With a chance of %0.00000000000512.<br>I'm completely aware of value of the life!",
        icon: "mdi-cake-variant",
      },
      {
        year: "2016",
        title: "Report to Record (R2R) - Month End",
        html: `
          <p>
          Development of month-end application using object-oriented design and programming concepts delivering following features:
              <ul>
                <li>Creating and scheduling monthly business activities/tasks</li>
                <li>Designate the monthly tasks, establish a workflow hierarchy and approval cycle for every activity</li>
                <li>Alerts and custom reminders for task assignments and task deadlines to the stakeholders via emails or internal notification system</li>
                <li>Produce month-end statistics reports to verify and track company's business activities and inform management and investors</li>
            </ul>
          </p>
          <p>
         Development of the R2R - Month End module and successful implementation in a crucial deadline helped the project team attract its first client.
          </p>
        `,
        image: "img/timeline/weatherford.png",
        iconImage: "img/timeline/tcs.png",
      },
      {
        year: "2017",
        title: "Contract Management System",
        html: `
          <p>
              Designed and developed UI screens, backend service architecture, and database for contract creation mechanism between a buyer and a vendor, along with mechanisms for its amendments and approval process.
          </p>
          <p>
            Rest API calls to communicate between buyers and vendors in the client-server system and approval work flow.
          </p>
          <p>
            Module Owner, Team leader, managing a team of 4-5 software developers. Mentoring junior developers.
          </p>
          <p>
          Requirements gathering, managing tasks allocations and task deadlines among team members, collaborating with cross-functional development teams, management, and business team to ensure successful and timely deliveries.
          </p>
        `,
        image: "img/timeline/manpower.png",
        iconImage: "img/timeline/tcs.png",
      },
      {
        year: "2018",
        title: "Invoice Management System",
        html: `
          <p>
              Designed and developed invoice creation, amendments and approvals features. Along with its own dynamic workflow management system.
          </p>
          <p>
            Created a resuable component to allow the developers easily create UI screens:
            <ul>
            <li>
            Developers could create entire UI screens simply by running a few database scripts.
            </li>
            <li>
            It saved a lot of coding efforts and the testing overhead for the developers. 
            </li>
            <li>
            Later, I had scaled up this component to be compatible with configuring UIs of different business logics.
            </li>
          </p>
        `,
        image: "img/timeline/tgb.png",
        iconImage: "img/timeline/tcs.png",
      },
      {
        year: "2019/20",
        title: "University of Regina - Cybersecurity Researcher",
        html: `
          <p>
              <ul>
              <li> Designing and modeling cybersecurity architecture, security systems and security-focused tools, mitigation plans, and algorithms for risk assessment and solve cybersecurity issues in cyber-physical systems.
              <li>Analyzed security vulnerabilities and developed security measures to mitigate cyber risks in smart grid.</li>
              <li>	Developed penetration testing tools to identify security weaknesses, and computing threat vectors. </li>
              <li> Designed security mechanisms for secure siting of embedded systems. </li>
              <li> Implemented the proposed cybersecurity architecture on an actual electric utility – the SaskPower grid of Saskatchewan province, to analyze the feasibility and accuracy of the architecture.</li>
              </ul>
          </p>
        `,
        image: "img/timeline/uofr.png",
        iconImage: "img/timeline/uofrIcon.jpg",
      },
      {
        year: "2021/22",
        title: "British Columbia Institute of Technology - Research Analyst",
        html: `
          <p>
              <ul>
              <li> Design, write, modify, integrate, and test full-stack software applications.
              <li>Identify technical problems and communicate effective strategies during proposal, technical due diligence, and/or design phases.</li>
              <li>Benchmark and debug critical issues, and participate in software design and code reviews. </li>
              <li> Assist in deploying, monitoring, and troubleshooting production systems. </li>
              <li> Develop and document APIs. Assist in developing logical and physical specifications.</li>
              <li>Prepare progress reports and manuals, summarize results, and present on project outcomes.</li>
              <li>Manage and respond to project related email, maintain notes and references in an organized manner.</li>
              </ul>
          </p>
        `,
        image: "img/timeline/bcit.png",
        iconImage: "img/timeline/BCIT_logo.png",
      },
    ],
    projectItems: [
      {
        text:
          "Designed and developed UI screens, backend service architecture, and database for contract creation mechanism between a buyer and a vendor, along with mechanisms for its amendments and approval process.",
      },
    ],
  }),
  computed: {
    orderedItems() {
      const items = [...this.items].reverse();
      if (this.detailed) return items;
      return items.filter((item) => {
        return !item.detailed;
      });
    },
  },
};
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.pre {
  white-space: pre;
}
.transparent {
  opacity: 0.6;
}
</style>
