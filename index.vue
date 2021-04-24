<template>
  <div>
  <v-container fill-height>
  <v-flex>
    <v-toolbar
    class="elevation-1">
      <v-spacer />
      <v-toolbar-title>
        <h2>SEND MESSAGE IN WHATSAPP WITHOUT SAVING NUMBER</h2>
      </v-toolbar-title>
      <v-spacer />
    </v-toolbar>
  </v-flex>
  </v-container>

    <v-container>
      <v-row justify="center" align="center">
      <v-flex class="flexContainer">
        <center><v-img :src="require('@/assets/wp.png')" height="140" width="140"></v-img></center><br>
        <v-text-field
                label="Enter Mobile Number"
                v-model="mobile"
                filled
                dense
            ></v-text-field>
          <spacer /><spacer />
          <center>
            <v-btn
              @click="createUrl"
              :href= "url"
              class="btn btn-info" 
              elevation="2"
              color="success">
              click me
            </v-btn>
          </center>
      </v-flex>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data: () => ({
      mobile: '',
      url: '#',
      dialog: false,
    }),
    methods: {
      createUrl() {
        if (this.mobile.length == 10){
          this.url = "http://wa.me/91"+this.mobile
          this.mobile = ''
        }
        else{
          this.mobile = ''
          alert("enter 10 digit mobile number")
        }
      }
    }
  }
  
</script>

<style>
  .first {
    margin: auto;
    width: 50%;;
    padding: 10px;
  }
    .flexContainer {
    max-width: 50% !important;
    overflow: auto;
}
</style>