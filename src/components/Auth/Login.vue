<template>
  <v-container fluid fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm8 md4>
        <v-card class="elevation-12">
          <v-toolbar dark color="primary">
            <v-toolbar-title>Login</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form ref="form" v-model="valid" validation>
              <v-text-field 
                prepend-icon="person" 
                name="email" 
                label="Email" 
                type="email"
                v-model="email"
                :rules="emailRules"
              ></v-text-field>
              <v-text-field 
                id="password" 
                prepend-icon="lock" 
                name="password" 
                label="Password"
                type="password"
                :counter="6"
                v-model="password"
                :rules="passwordRules"
              ></v-text-field>
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="primary"
              @click="onSubmit"
              :disabled="!valid"
            >Login</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        email: '',
        password: '',
        valid: false,
        emailRules: [
          value => !!value || 'E-mail is required',
          value => {
            if (value.length > 0) {
              const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
              return pattern.test(value) || 'Invalid e-mail'
            }
          }
        ],
        passwordRules: [
          value => !!value || 'Password is required',
          value => (value && value.length >= 6) || 'Password must be equal or more than 6 characters'
        ]
      }
    },
    methods: {
      onSubmit () {
        if (this.$refs.form.validate()) {
          const user = {
            email: this.email,
            password: this.password
          }
          console.log(user)
        }
      }
    }
  }
</script>