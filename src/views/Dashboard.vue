<template>
<div class="Dashboard">
  <h1 class="subtitle-1 grey--text mt-4">Dashboard</h1>

    

  <v-container class="mt-5">

      <v-layout row wrap>
        <v-tooltip top>
            <template v-slot:activator="{on}">
                <v-btn small text color="grey" @click="sortBy('title')" v-on="on">
                    <v-icon left small>folder</v-icon>
                    <span class="caption">By project name</span>
                </v-btn>
            </template>
        <span>Sort projects by project name</span>
        </v-tooltip>
        <v-tooltip top>
            <template v-slot:activator="{on}">
                <v-btn small text color="grey" @click="sortBy('person')" v-on="on">
                <v-icon left small>person</v-icon>
                <span class="caption">By person</span>
                </v-btn>
            </template>   
        <span>Sort projects by person</span>
        </v-tooltip>
    </v-layout>

      <v-card :class="`project ${project.status} pa-5 mt-2`" v-for="project in projects" :key="project.title">
          <v-layout row wrap>
              <v-flex xs12 md6>
                  <div class="grey--text caption">Project title</div>
                  <div>{{project.title}}</div>
              </v-flex>
              <v-flex xs6 sm4 md2>
                  <div class="grey--text caption">Person</div>
                  <div>{{project.person}}</div>
              </v-flex>
              <v-flex xs6 sm4 md2>
                  <div class="grey--text caption">Due by</div>
                  <div>{{project.due}}</div>
              </v-flex>
              <v-flex xs2 sm4 md2>
                  <div class="text-right">
                      <v-chip small :class="`${project.status} white--text my-2`">
                          {{project.status}}
                      </v-chip>
                  </div>
              </v-flex>
          </v-layout>
      </v-card>
  </v-container>
</div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Dashboard',
  data () {
      return {
          projects: [
            { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
            { title: 'Code up the homepage', person: 'Chun Li', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
            { title: 'Design video thumbnails', person: 'Ryu', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
            { title: 'Create a community forum', person: 'Gouken', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
          ]
      }
  },
  methods: {
      sortBy(prop) {
          this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1); 
      }
  }
}
</script>


<style>
    .project.complete{
        border-left: 4px solid green;
    }
    .project.ongoing{
        border-left: 4px solid indigo;
    }
    .project.overdue{
        border-left: 4px solid red;
    }
    .v-chip.complete{
        background: green!important;
    }
    .v-chip.ongoing{
        background: indigo!important;
    }
    .v-chip.overdue{
        background: red!important;
    }
</style>