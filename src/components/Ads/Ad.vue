<template>
  <v-container>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3 md8 offset-md2>
        <v-card
          class="elevation-3 mb-3 pa-2"          
        >          
          <v-flex>
            <v-img
              src="https://images.unsplash.com/photo-1544220830-7da42df1ff8d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
              height="320"
            ></v-img>
          </v-flex>
          <v-flex>
            <v-card-text>
              <h2 class="text--primary">Heading</h2>
              <p>Paragraph</p>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn
                class="info mr-2"
              >Edit</v-btn>
              <v-btn
                class="error"
              >Buy Advertising</v-btn>
            </v-card-actions>
          </v-flex>         
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {}
    }
  }
</script>