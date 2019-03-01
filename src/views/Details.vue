<template>
<v-card dark color="blue-grey">
  <v-form v-model="valid">
    <v-container>
      <v-layout row wrap>
        <v-flex
          xs12

        >
        <v-text-field
          v-model="title"
          label="Title"
          prepend-icon="title"
          box
          required
          :disabled="disableEdit"

        ></v-text-field>
      </v-flex>

      <v-flex
        xs12


      >
      <v-text-field
        v-model="description"
        label="Description"
        prepend-icon="description"
        box
        required
        :disabled="disableEdit"

      ></v-text-field>
    </v-flex>

    <v-flex
      xs4


    >
    <v-text-field
      v-model="city"
      label="City"
      prepend-icon="location_city"
      box
      required
      :disabled="disableEdit"

    ></v-text-field>
  </v-flex>

    <v-flex
      xs8


    >
    <v-text-field
      v-model="place"
      label="Place"
      prepend-icon="place"
      box
      required
      :disabled="disableEdit"

    ></v-text-field>
  </v-flex>

      <v-flex
        xs12
        md4
      >
      <v-text-field
        v-model="date"
        label="Date"
        prepend-icon="date_range"
        placeholder="29 березня 2019"
        box
        required
        :disabled="disableEdit"

      ></v-text-field>
    </v-flex>

    <v-flex
      xs12
      md4
    >
    <v-text-field
      v-model="registrationtime"
      label="Registration Time"
      prepend-icon="av_timer"
      placeholder="13:00"
      box
      required
      :disabled="disableEdit"

    ></v-text-field>
  </v-flex>

    <v-flex
      xs12
      md4
    >
    <v-text-field
      v-model="starttime"
      label="Start Time"
      prepend-icon="access_time"
      placeholder="14:00"
      box
      required
      :disabled="disableEdit"

    ></v-text-field>
  </v-flex>

  <v-flex
    xs12
    md12
  >
  <v-textarea
  name="input-comments"
  box
  label="Comments"
  auto-grow
  value=""
  :disabled="disableEdit"

></v-textarea>
  </v-flex>
  <v-flex
    xs12
    md12
  >
    <v-divider color="white"></v-divider>
    <v-spacer></v-spacer>
<v-btn color="warning" small @click="disableEdit = !disableEdit">Edit</v-btn>
  </v-flex>


      </v-layout>
    </v-container>
  </v-form>
</v-card>

</template>
<script>
  export default {
    props: {event: Object},
    data: () => ({
      disableEdit: true,
      valid: false,
      title: '',
      description: '',
      city: '',
      place: '',
      date: '',
      registrationtime: '',
      starttime: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 10 || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ]
    })
  }
</script>
