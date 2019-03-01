<template>
<v-app>

  <v-toolbar app dark color="primary">
    <v-toolbar-title class="headline text-uppercase">
      <v-img src="/assets/logo-de.png">
      </v-img>
      <span>Event</span>
      <span class="font-weight-light">Manager</span>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn flat href="http://elt.dinternal.com.ua" target="_blank">
      <span class="mr-2">ELT</span>
    </v-btn>
    <v-btn flat href="https://shop.dinternal.com.ua" target="_blank">
      <span class="mr-2">SHOP</span>
    </v-btn>
    <v-btn flat href="http://timetable:2000/" target="_blank">
      <span class="mr-2">Timetable</span>
    </v-btn>
  </v-toolbar>

  <v-content>
    <!-- <HelloWorld/> -->
    <!-- <router-link :to="{ name: 'about', params: {} }">About</router-link> -->
    <v-container fluid grid-list-md>
      <v-layout>
        <v-flex xs12 md6>
          <h3 class="mb-3 text-lg-center">EVENTS LIST</h3>
          <EventList
          :events="events"
          @copy="copyToNewEvent"
          @more="more"
          @edit="editEvent"
          />
        </v-flex>
        <!-- <v-flex text-xs-center xs12 md6> -->
        <v-flex xs12 md6 >
          <h3 class="mb-3 text-lg-center" >DETAILS</h3>
          <Details :event="events[currentID]" v-show="showDetails"/>
        </v-flex>
      </v-layout>
    </v-container>

    <v-container fluid>
      <v-layout justify-end row>
      <v-flex xs12>
        <v-btn
          fixed
          dark
          fab
          bottom
          right
          color="pink"
          class="mb-5 mr-4"
          @click="addEvent(1)"
        >
          <v-icon dark>add</v-icon>
        </v-btn>
      </v-flex>
      </v-layout>
    </v-container>

  </v-content>

  <v-footer class="pa-3" color="indigo" app>
    <v-spacer></v-spacer>
    <div class="white--text">Dinternal-Education &copy; {{ new Date().getFullYear() }}</div>
  </v-footer>

</v-app>
</template>

<script>
import EventList from './views/EventList'
import Details from './views/Details'

export default {
  name: 'App',
  components: {
    EventList, Details
  },
  data() {
    return {
      showDetails: false,
      currentID: '',
      events: [{
          id: 0,
          title: 'Dinternal Education Fest 2019',
          description: 'Фестиваль нестандартних та дієвих ідей навчання англійської мови у сучасній українській школі',
          date: '21 березня 2019',
          time: '13:00',
          city: 'Новоград-Волинський',
          place: 'вул. Тестова 21',
          methodologists: [0, 2]
        },
        {
          id: 1,
          title: 'Incorporating ZNO preparation best practices into a standard 45-min lesson',
          description: 'Ефективне поєднання навчання загальної англійської в старших класах та підготовки до ЗНО з англійської мови',
          date: '29 березня 2019',
          time: '13:00',
          city: 'Житомир',
          place: 'вул. Тестова 21',
          methodologists: [1]
        },
        {
          id: 2,
          title: 'Incorporating ZNO preparation best practices into a standard 45-min lesson',
          description: 'Ефективне поєднання навчання загальної англійської в старших класах та підготовки до ЗНО з англійської мови',
          date: '02 квітня 2019',
          time: '13:00',
          city: 'Хмельницький',
          place: 'вул. Тестова 21',
          methodologists: [2]
        },
        {
          id: 3,
          title: 'Incorporating ZNO preparation best practices into a standard 45-min lesson',
          description: 'Ефективне поєднання навчання загальної англійської в старших класах та підготовки до ЗНО з англійської мови',
          date: '02 april 2019',
          city: 'Харків',
          methodologists: [0]
        },
        {
          id: 4,
          title: 'Incorporating ZNO preparation best practices into a standard 45-min lesson',
          description: 'Ефективне поєднання навчання загальної англійської в старших класах та підготовки до ЗНО з англійської мови',
          date: '02 april 2019',
          city: 'Хмельницький',
          methodologists: [1]
        },
        {
          id: 5,
          title: 'Incorporating ZNO preparation best practices into a standard 45-min lesson',
          description: 'Ефективне поєднання навчання загальної англійської в старших класах та підготовки до ЗНО з англійської мови',
          date: '02 april 2019',
          city: 'Хмельницький',
          methodologists: [1]
        }
      ],
      methodologists: [{
        firstName: 'Svitlana',
        lastName: 'Sorochynska'
      }]
    }
  },
  computed: {
    event: () => this.events[this.currentID]
  },
  methods: {
    addEvent(id) {
      console.log(id);
    },
    more(id) {
      this.currentID = id;
      this.showDetails = !this.showDetails;
    },
    copyToNewEvent(id){
      console.log('copyToNewEvent '+id);
    },
    editEvent(id){
      console.log('editEvent '+id);
    },
  }
}
</script>
