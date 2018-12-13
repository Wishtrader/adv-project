<template>
  <v-container>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3>
        <h1 class="text--secondary mb-3">My advertisements</h1>
        <v-card
          class="elevation-3 mb-3 pa-2"
          v-for="add in ads"
          :key="add.id"
        >
          <v-layout row>
            <v-flex xs4>
              <v-img
                :src="add.imageSrc"
                height="160"
              ></v-img>
            </v-flex>
            <v-flex xs8>
              <v-card-text>
                <h2 class="text--primary">{{add.title}}</h2>
                <p>{{add.description}}</p>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  class="info mr-4"
                  :to="'/ad/' + add.id"
                >Open</v-btn>
              </v-card-actions>
            </v-flex>
          </v-layout>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        ads: [
          {
            title: 'First Add',
            description: 'Description',
            promo: false,
            imageSrc: 'https://images.unsplash.com/photo-1544220830-7da42df1ff8d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
            id: '001'
          },
          {
            title: 'Second Add',
            description: 'Description',
            promo: true,
            imageSrc: 'https://images.unsplash.com/photo-1543964198-d54e4f0e44e3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
            id: '002'
          },
          {
            title: 'Third Add',
            description: 'Description',
            promo: true,
            imageSrc: 'https://images.unsplash.com/photo-1519044912065-7295b0fef116?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
            id: '003'
          }
        ]
      }
    }
  }
</script>