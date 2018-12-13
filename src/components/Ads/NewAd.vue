<template>
  <v-container>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3>
        <h1 class="text--secondary mb-3">Cteate new advertising</h1>
        <v-form ref="form" v-model="valid" validation class="mb-3">
          <v-text-field
            name="title" 
            label="Ad title" 
            type="text"
            v-model="title"
            required
            :rules="[v => !!v || 'Title is required']"
          ></v-text-field>
          <v-textarea 
            name="description" 
            label="Ad description"
            type="text"
            v-model="description"
            required
            :rules="[v => !!v || 'Description is required']"
          ></v-textarea>
        </v-form>
        <v-layout row mb-3>
          <v-flex xs12>
            <v-btn color="info">
              Upload
              <v-icon right dark>cloud_upload</v-icon>
            </v-btn>
          </v-flex>
        </v-layout>
        <v-layout row ml-2>
          <img src="">
        </v-layout>
        <v-layout row ml-2>
          <v-flex xs12>
            <v-switch color="info"
              label="Add to promo?"
              v-model="promo"
            ></v-switch>
          </v-flex>
        </v-layout>
        <v-layout row >
          <v-flex xs12>
            <v-spacer></v-spacer>
            <v-btn
              :disabled="!valid"
              class="success"
              @click="createAd"
            >Create Ad</v-btn>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        title: '',
        description: '',
        promo: false,
        valid: false
      }
    },
    methods: {
      createAd () {
        if (this.$refs.form.validate()) {
        }
      }
    }
  }
</script>