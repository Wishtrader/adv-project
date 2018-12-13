<template>
  <div>
    <v-container fluid>
      <v-layout row>
        <v-flex xs12>
          <v-carousel>
            <v-carousel-item
              v-for="add in ads"
              :key="add.id"
              :src="add.imageSrc"
            >
              <div class="carousel-link">
                <v-btn class="error" :to="'/add/' + add.id">{{add.title}}</v-btn>
              </div>
            </v-carousel-item>
          </v-carousel>
        </v-flex>
      </v-layout>
    </v-container>
    <v-container grid-list-lg>
      <v-layout row wrap>
        <v-flex 
          xs12
          md4
          sm6
          v-for="add in ads"
          :key="add.id"
        >
          <v-card>
            <v-img
              :src="add.imageSrc"
              height="200px"
            >
            </v-img>

            <v-card-title primary-title>
              <div>
                <div class="headline">{{add.title}}</div>
                <span class="grey--text">{{add.description}}</span>
              </div>
            </v-card-title>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn class="success" flat :to="'/add/' + add.id">Open</v-btn>
              <v-btn raised class="primary">Buy</v-btn>
             
              <v-btn icon @click="show = !show">
                <v-icon>{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-slide-y-transition>
              <v-card-text v-show="show">
                I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
              </v-card-text>
            </v-slide-y-transition>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
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

<style scoped>
  .carousel-link {
    position: absolute;
    bottom: 50px;
    left: 50%;
    transform: translate(-50%, 0);
    border-radius: 5px;
  }

</style>
