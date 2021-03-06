<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
      height="100"
    >
      <v-avatar
        class="mr-3"
        
        size="70"
      >
        <v-img
          contain
          max-height="70%"
          :src="require('./assets/Logo.png')"
        ></v-img>
      </v-avatar>

      <v-toolbar-title class="font-weight-black headline">
        CALTHASOFT L.L.C.
      </v-toolbar-title>
    </v-app-bar>

    <v-main>
      <section id="hero">
        <v-row no-gutters>
          <v-img
            :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
            src="https://images.unsplash.com/photo-1487017159836-4e23ece2e4cf?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1951&q=80"
          >
            <v-theme-provider dark>
              <v-container fill-height>
                <v-row
                  align="center"
                  class="white--text mx-auto"
                  justify="center"
                >
                  <v-col
                    class="white--text text-center"
                    cols="12"
                    tag="h1"
                  >
                    <span
                    :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
                      class="font-weight-light"
                    >
                      WELCOME TO
                    </span>

                    <br>

                    <span
                      :class="[$vuetify.breakpoint.smAndDown ? 'display-3': 'display-4']"
                      class="font-weight-black"
                    >
                      CALTHASOFT
                    </span>

                  </v-col>

                  <v-btn
                    class="align-self-end"
                    fab
                    outlined
                    @click="$vuetify.goTo('#about-me')"
                  >
                    <v-icon>mdi-chevron-double-down</v-icon>
                  </v-btn>
                </v-row>
              </v-container>
            </v-theme-provider>
          </v-img>
        </v-row>
      </section>
      <section id="about-me">
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">About Us</h2>

          <v-responsive
            class="mx-auto mb-8"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            At Calthasoft we strive to create software solutions that stand out from the crowd. We follow agile development practices with fast iteration cycles and goal-oriented development process. We specialize in web-based architectures based on proven industry practices to deliver simple and beautiful software that does the right thing. No more, no less.
          </v-responsive>

          <v-avatar
            class="elevation-12 mb-12"
            size="128"
          >
            <v-img :src="require('./assets/dfimiarz.jpg')"></v-img>
          </v-avatar>

          <div></div>

          <v-btn
            color="grey"
            @click="$vuetify.goTo('#projects')"
            outlined
            large
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              Recent Projects
            </span>
          </v-btn>
        </v-container>

        <div class="py-12"></div>
      </section>

      <section
        id="features"
        class="grey lighten-3"
      >
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">How We Work</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-row>
            <v-col
              v-for="({ icon, title, text }, i) in features"
              :key="i"
              cols="12"
              md="4"
            >
              <v-card
                class="py-12 px-4"
                color="grey lighten-5"
                flat
              >
                <v-theme-provider dark>
                  <div>
                    <v-avatar
                      color="primary"
                      size="88"
                    >
                      <v-icon
                        large
                        v-text="icon"
                      ></v-icon>
                    </v-avatar>
                  </div>
                </v-theme-provider>

                <v-card-title
                  class="justify-center font-weight-black text-uppercase"
                  v-text="title"
                ></v-card-title>

                <v-card-text
                  class="subtitle-1"
                  v-text="text"
                >
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>

        <div class="py-12"></div>
      </section>

      <section id="stats">
        <v-parallax
          :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
          src="https://images.unsplash.com/photo-1510915228340-29c85a43dcfe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
        >
          <v-container fill-height>
            <v-row class="mx-auto">
              <v-col
                v-for="[value, title] of stats"
                :key="title"
                cols="12"
                md="4"
              >
                <div class="text-center">
                  <div
                    class="display-3 font-weight-black mb-4"
                    v-text="value"
                  ></div>

                  <div
                    class="title font-weight-regular text-uppercase"
                    v-text="title"
                  ></div>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-parallax>
      </section>

      <section id="projects">
        <div class="py-12"></div>

        <v-container>
          <h2 class="display-2 font-weight-bold mb-3 text-center">Recent Projects</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-row>
            <v-col
              v-for="({ src, text, title,page }, i) in projects"
              :key="i"
              cols="12"
              md="4"
            >
              <v-img
                :src="require('./assets/' + src)"
                class="mb-4"
                height="275"
                max-width="100%"
                contain
              ></v-img>

              <h3
                class="font-weight-black mb-4 text-uppercase"
                v-text="title"
              ></h3>

              <div
                class="title font-weight-light mb-5"
                v-text="text"
              ></div>

              <v-btn
                class="ml-n4 font-weight-black"
                text
                :disabled="! page"
              >
                Project Page
              </v-btn>
            </v-col>
          </v-row>
        </v-container>

        <div class="py-12"></div>
      </section>

      <v-sheet
        id="contact"
        color="#333333"
        dark
        tag="section"
        tile
      >
        <div class="py-12"></div>

        <v-container>
          <h2 class="display-2 font-weight-bold mb-3 text-center">Contact Us</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-theme-provider light>
            <v-row justify="center">
              <v-col cols="12">
                <v-text-field
                  flat
                  label="Name*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-text-field
                  flat
                  label="Email*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-text-field
                  flat
                  label="Subject*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-textarea
                  flat
                  label="Message*"
                  solo
                ></v-textarea>
              </v-col>

              <v-col
                class="mx-auto"
                cols="auto"
              >
                <v-btn
                  color="accent"
                  x-large
                  disabled
                >
                  Submit
                </v-btn>
              </v-col>
            </v-row>
          </v-theme-provider>
        </v-container>
         <div class="py-12"></div>
      </v-sheet>
    </v-main>
    <v-footer
      class="justify-center"
      color="#292929"
      height="100"
    >
      <div class="title font-weight-light grey--text text--lighten-1 text-center">
        &copy; {{ (new Date()).getFullYear() }} — Calthasoft, L.L.C.
      </div>
    </v-footer>
  </v-app>
</template>

<script>


export default {
  name: 'App',

  components: {
    
  },

  data: () => ({
        projects: [
          {
            src: 'CalthasoftLLC.jpg',
            title: 'Calthasoft Website',
            text: 'Our website implemented with Vue.js and Vuetify deployed on Google Firebase. Under construction.',
            page: null
          },
          {
            src: 'Clubhouse.jpg',
            title: 'Clubhouse',
            text: 'Open source tennis club managment platform. Built in Vue.js with Express, Redis, MySQL based REST API backend.',
            page:  null
          },
          {
            src: 'Birdcolony.jpg',
            title: 'Birdcolony',
            text: 'A plaform for managing a bird colony. Tracking colony resources including nest, birds, eggs, and overall colony infrastructure. Deployed on Google Cloud Infrastructure.',
            page: null
          }
        ],
        features: [
          {
            icon: 'mdi-laptop',
            title: 'Software Expertise',
            text: 'We like full-stack software solutions based on modern front-end frameworks like Vue, React. Backend technologies follow REST API practices interfacing with relational and NoSQL databases.',
          },
          {
            icon: 'mdi-account-multiple',
            title: 'People',
            text: 'We are a small team of developers with multiple years of software development experience. We embrace the everchanging industry and do not shy away from learning. We are curious, we innovate, we "JUST GET IT DONE"',
          },
          {
            icon: 'mdi-face-agent',
            title: 'Agile Development',
            text: 'We take pride in our work. We focus on fast development cycles and delivering viable solutions that show results in a short time frames. Such process allows our customers to gauge progress and make stratigic changes quickly without the need for long meetings and headaches of overplanning.',
          },
        ],
        stats: [
          ['10+', 'Years of experience'],
          ['5', 'Projects in production'],
          ['1000+', 'Users across projects']
        ],
      }),
};
</script>
