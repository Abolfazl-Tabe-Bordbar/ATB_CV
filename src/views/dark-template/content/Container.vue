<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="Who am I?"
      >
        Hello my friend
        My name is Abolfazl Tabe Bardbar, a web programmer and interested in the field of programming.
      </content-section>
      <content-section
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
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    // prouds: [
    //   {
    //     icon  : 'mdi-help-rhombus-outline',
    //     text  : 'Answered 10M+ questions!',
    //     source: '(Bytegate.ir post views)',
    //   },
    //   {
    //     icon  : 'mdi-library-music',
    //     text  : 'Made people enjoy and learn a new language for equivalent of 29+ years (older than myself!)',
    //     source: '(Bobet.ir and its channel downloads)',
    //   },
    //   {
    //     icon  : 'mdi-timer-sand',
    //     text  : 'Saved +110 days of time of students, writers and etc!',
    //     source: '(Delix.ir service usages)',
    //   },
    //   {
    //     icon  : 'mdi-account-multiple',
    //     text  : 'Tried to cover small part of 7 people expenses.',
    //     source: '(My awesome colleagues)',
    //   },
    // ],
    // educations: [
    //   {
    //     from       : '2015',
    //     to         : '2019 (not finished yet)',
    //     title      : 'Bachelor\'s degree, Information Technology',
    //     location   : 'Seraj University',
    //     description: 'Became a member of University Academic Association of Computer Science',
    //   },
    // ],
    skills: [
      {
        title: 'PHP',
        icon : 'mdi-language-php2',
        value: 80,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript2',
        value: 80,
      },
      {
        title: 'Laravel Framework',
        icon : 'mdi-laravel2',
        value: 50,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-2vuejs',
        value: 80,
      },
      { divider: true },
      {
        title: 'Git/Github',
        icon : 'mdi-git2',
        value: 80,
      },
      {
        title: 'HTML',
        icon : 'mdi-HTML5',
        value: 80,
      },
      {
        title: 'CSS',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'SCSS',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Bootstrap',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Tailwindcss',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Bulma',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Typescript',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Nuxt.js',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Node.js',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'C#',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Express.js',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Word Press',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'VueX/Pini',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'MVC',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'JQuery',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'PostgreSql',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'MySql',
        icon : 'mdi-css',
        value: 80,
      },{
        title: 'React.js',
        icon : 'mdi-css',
        value: 80,
      },{
        title: 'Next.js',
        icon : 'mdi-css',
        value: 80,
      },{
        title: 'Redis',
        icon : 'mdi-css',
        value: 80,
      },{
        title: 'Dart',
        icon : 'mdi-css',
        value: 80,
      },
      {
        title: 'Redux toolkit',
        icon : 'mdi-css',
        value: 80,
      },{
        title: 'Rest API',
        icon : 'mdi-css',
        value: 80,
      },
      { divider: true },
      { divider: true },
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
