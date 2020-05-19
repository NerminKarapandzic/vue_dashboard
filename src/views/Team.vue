<template>
<div class="Team">
  <h1 class="subtitle-1 grey--text mt-4">Team</h1>

  <v-container class="mt-5">
      <v-layout row wrap>
          <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
              <v-card class="ma-3 text-center">
                  <v-avatar class="mt-4" size="100px" >
                      <img :src="person.avatar" alt="alt" style="border-radius:50%;">
                  </v-avatar>
                  <v-card-text>
                      <div class="subtitle-1">{{person.name}}</div>
                      <div class="subtitle-2 grey--text">{{person.role}}</div>
                  </v-card-text>
                  <v-card-actions>
                      <v-spacer></v-spacer>
                      <v-btn text color="grey">
                          <v-icon>message</v-icon>
                          <span>Message</span>
                      </v-btn>
                      <v-spacer></v-spacer>
                  </v-card-actions>
              </v-card>
          </v-flex>
      </v-layout>
  </v-container>
</div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Team',
  data() {
      return {
          team: [
                { name: 'The Net Ninja', role: 'Web developer', avatar: '/avatar.jpg' },
                { name: 'Ryu', role: 'Graphic designer', avatar: '/avatar.jpg' },
                { name: 'Chun Li', role: 'Web developer', avatar: '/avatar.jpg' },
                { name: 'Gouken', role: 'Social media maverick', avatar: '/avatar.jpg' },
                { name: 'Yoshi', role: 'Sales guru', avatar: '/avatar.jpg'}
            ]
      }
  }
}
</script>
