<template>
  <section class="section section-home">
    <div class="main-img">
      <img 
        class="hacktoberfest-img" 
        src="/hacktoberfest.svg" 
        alt="Hacktoberfest Frankfurt">
    </div>
    <ul class="list list-stats">
      <li 
        v-for="stat in stats"
        :key="stat.index" 
        class="list-item">
        <div class="stat-number">{{ stat.number }}</div>
        <div class="stat-name">{{ stat.name }}</div>
      </li>
    </ul>
    <article class="article article-community">
      <list-component 
        :items="communities" 
        :item-type="'community'" 
        class="community-list"/>
      <h2 class="sponsor-heading">Sponsored by</h2>
      <list-component 
        :items="sponsors" 
        :item-type="'sponsor'" 
        class="sponsor-list"/>
    </article>
  </section>
</template>

<script>
import ListComponent from "@/components/ListComponent";
import { mapActions } from "vuex";
export default {
  name: "Home",
  components: {
    ListComponent
  },
  data: () => ({
    sponsors: [
      {
        name: "melsicon",
        url: "https://melsicon.de",
        img: "./sponsors/melsicon.svg"
      },
      {
        name: "rocketloop",
        url: "https://rocketloop.de",
        img: "./sponsors/rocketloop.svg"
      },
      {
        name: "mindspace",
        url: "https://mindspace.me",
        img: "./sponsors/mindspace.svg"
      },
      {
        name: "msg",
        url: "https://msg.group",
        img: "./sponsors/msg.svg"
      },
      {
        name: "codemonauts",
        url: "https://codemonauts.com",
        img: "./sponsors/codemonauts.svg"
      },
      {
        name: "uib GmbH",
        url: "https://uib.de",
        img: "./sponsors/uib.svg"
      },
      {
        name: "quokkajs",
        url: "https://quokkajs.com",
        img: "./sponsors/quokkajs.svg"
      },
      {
        name: "DigitalOcean",
        url: "https://digitalocean.com",
        img: "./sponsors/digitalocean.svg"
      },
      {
        name: "GitHub",
        url: "https://github.com",
        img: "./sponsors/github.svg"
      },
      {
        name: "Twilio",
        url: "https://twilio.com",
        img: "./sponsors/twilio.svg"
      }
    ],
    communities: [
      {
        name: "Angular Frankfurt",
        url: "https://www.meetup.com/Angular-Frankfurt/"
      },
      {
        name: "ASP.NET Core Rhein Main",
        url: "https://www.meetup.com/NET-Core-Rhein-Main/"
      },
      {
        name: "Code Review",
        url: "https://www.meetup.com/code-review/"
      },
      {
        name: "CSS Frankfurt",
        url: "https://cssfrankfurt.de"
      },
      {
        name: "Elixir Meetup Rhein Main",
        url: "https://www.meetup.com/Elixir-Meetup-Rhein-Main/"
      },
      {
        name: "Frankfurt Data Science",
        url: "https://www.meetup.com/FrankfurtDataScience/"
      },
      {
        name: "Frontend RheinMain",
        url: "https://www.meetup.com/frontend_rm/"
      },
      {
        name: "GDG Rhein Main",
        url: "https://www.meetup.com/gdgrheinmain/"
      },
      {
        name: "Vue.js Frankfurt",
        url: "https://meetup.com/vuejsfrankfurt"
      },
      {
        name: "Techettes Frankfurt",
        url: "https://www.meetup.com/Techettes/"
      },
      {
        name: "Women Techmakers Rhein-Main",
        url: "https://www.meetup.com/Women-Techmakers-Frankfurt_Rhein-Main/"
      }
    ]
  }),
  computed: {
    stats() {
      const statsArray = [
        {
          name: "Communities",
          number: "10+"
        },
        {
          name: "Participants",
          number: "140+"
        },
        {
          name: "Sponsors",
          number: this.sponsors.length
        }
      ];
      return statsArray;
    }
  },
  methods: {
    ...mapActions({
      login: "login/login"
    })
  }
};
</script>

<style lang="sass">

  .section-home
    min-height: 100vh

  .main-img
    max-width: 500px
    text-align: center
    margin: auto

  .hacktoberfest-img
    width: 100%

  .list-stats
    flex-basis: 100%
    text-align: center
    padding-bottom: .5rem
    max-width: 700px
    margin: 0 auto
    justify-content: center

    .list-item
      margin: 0 1.5rem

  .stat-number
    font-size: 2.5rem
    font-weight: 700

  .stat-name, .sponsor-heading
    text-align: center
    text-transform: uppercase
    font-size: .9rem
    font-weight: 700
    letter-spacing: 1px
    opacity: .7

</style>
