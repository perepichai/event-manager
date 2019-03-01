<template>
<div>
  <v-layout column>
    <v-flex mb-2 v-for="event in events" :key="event.id">
      <v-card>
        <v-card-title primary-title>
          <v-layout row>
            <v-flex xs12 md8 lg9>
              <div>
                <!-- <h4 class="headline mb-0">{{events[0].title}}</h4> -->
                <div class="title mb-2">{{event.title}}</div>
                <div>
                  <v-chip>
                    <v-avatar class="teal">
                      <img src="../assets/sorochynska.jpg" alt="sorochynska"></v-avatar>
                    Sorochynska
                  </v-chip>
                  <v-chip>
                    <v-avatar class="teal">
                      <img src="../assets/bilous.jpg" alt="bilous"></v-avatar>
                    Bilous
                  </v-chip>
                </div>

              </div>
            </v-flex>

            <v-flex xs12 md4 lg3>
              <v-spacer></v-spacer>
              <div>
                <div class="grey--text mb-1">
                  <v-icon>date_range</v-icon> {{event.date}}
                </div>
                <!-- <div class="grey--text text-lg-right" ><v-icon>place</v-icon> {{events[0].city}}</div></div> -->
                <div class="grey--text">
                  <v-icon>place</v-icon> {{event.city}}
                </div>
              </div>
            </v-flex>
          </v-layout>
        </v-card-title>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn flat color="primary" small @click="more(event.id)">More</v-btn>
          <v-btn flat color="warning" small @click="edit(event.id)">Edit</v-btn>
          <v-btn flat color="teal" small @click="copy(event.id)">Copy to new event</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>

  </v-layout>

</div>
</template>

<script>
export default {
  props: {events: Array},
  data() {
    return {
      methodologists: [{
        firstName: 'Svitlana',
        lastName: 'Sorochynska'
      }]
    }
  },
  methods: {
    copy(id) {
      this.$emit('copy', id)
    },
    edit(id) {
      this.$emit('edit', id)
    },
    more(id) {
      this.$emit('more', id)
    }
  }
}
</script>
