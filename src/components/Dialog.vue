<template>
    <v-dialog v-model="dialog" max-width="600" >
      <template v-slot:activator="{ on }">
        <v-btn text class="white--text cyan" dark v-on="on">
          Create new project
        </v-btn>
      </template>

      <v-card>
        <v-card-title primary-title >
          Create new project
        </v-card-title>

        <v-card-text>
            <v-form ref="form">
                <v-text-field name="title"  label="Title" id="title" :rules="inputRules" v-model="title" prepend-icon="folder"></v-text-field>
                <v-textarea name="content" label="Content" id="content" v-model="content" prepend-icon="edit"></v-textarea>

                <v-menu offset-y>
                <template v-slot:activator="{ on }">
                    <v-text-field :value="due" label="Due by" v-on="on" prepend-icon="date_range" ></v-text-field >
                </template>
                <v-date-picker v-model="due" ></v-date-picker>
                </v-menu>

                <v-btn text class="mx-5 cyan white--text" @click="submit">Add project</v-btn>
            </v-form>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
        </v-card-actions>
      </v-card>
    </v-dialog>
</template>

<script>
export default {
    data(){
        return {
            title: '',
            content: '',
            due: '',
            inputRules: [
                v => v.length >= 3 || 'Minimum number of characters is 3'
            ]
        }
    },
    methods: {
        submit(){
            if(this.$refs.form.validate()){
                console.log(this.title, this.content);
            }
        }
    }
}
</script>