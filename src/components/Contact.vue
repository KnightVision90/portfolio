<template>
  <div id="contact" class="text-xs-center">
    <h3>I'm Available</h3>
    <h4>Let's Work Together!</h4>
    <h5>Have a job or project you think I could help with?<br>Feel free to reach out and let me know!</h5>
    <div id="contact-form">
      <v-container>
        <v-row>
          <v-col xs12>
            <v-card>
              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col xs4 md2 lg1>
                      <v-subheader>Name</v-subheader>
                    </v-col>
                    <v-col xs8 md10 lg5>
                      <v-text-field
                        ref="nameField"
                        v-model="name"
                        label="Name"
                        required
                        maxlength="50"
                      ></v-text-field>
                    </v-col>

                    <v-col xs4 md2 lg1>
                      <v-subheader>Email</v-subheader>
                    </v-col>
                    <v-col xs8 md10 lg5>
                      <v-text-field
                        ref="emailField"
                        v-model="email"
                        label="Email"
                        required
                        :rules="emailValidation"
                      ></v-text-field>
                    </v-col>

                    <v-col xs4 md2>
                      <v-subheader>Message</v-subheader>
                    </v-col>
                    <v-col xs8 md10>
                      <v-text-field
                        ref="messageField"
                        v-model="message"
                        label="Message"
                        multi-line
                        required
                      ></v-text-field>
                    </v-col>
                    <v-col xs12>
                      <v-btn light default @click.native="sendEmail">Submit</v-btn>
                    </v-col>
                  </v-row>
                </v-container>
                <v-alert :error="emailFailed" :success="!emailFailed" :value="status">{{ status }}</v-alert>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';

  export default {
    name: 'contact',
    data() {
      return {
        myEmail: 'joseph.moraniii@gmail.com',
        formAction: 'https://formspree.io/',
        name: '',
        email: '',
        message: '',
        status: '',
        emailFailed: false,
        emailValidation: [(value) => {
          const rule = /\S+@\S+\.\S+/;
          return !value || rule.test(value) ? true : 'Email is not valid.';
        }],
      };
    },
    methods: {
      resetForm() {
        this.email = '';
        this.name = '';
        this.message = '';
      },
      sendEmail() {
        if (!this.validateForm()) {
          this.emailFailed = true;
          this.status = 'Please fix the invalid inputs.';
          return false;
        }

        axios.post(
          this.formAction + this.myEmail,
          {
            name: this.name,
            email: this.email,
            message: this.message,
          },
        ).then(() => {
          this.status = 'Email sent!';
          this.emailFailed = false;
          this.resetForm();
        }).catch(() => {
          this.status = `Something went wrong. Try contacting me directly at ${this.myEmail}.`;
          this.emailFailed = true;
        });
        return false;
      },
      validateForm() {
        return !(!this.name.trim() ||
        this.$refs.nameField.hasError ||
        !this.email.trim() ||
        this.$refs.emailField.hasError ||
        !this.message.trim() ||
        this.$refs.messageField.hasError);
      },
    },
  };
</script>

<style lang="scss" scoped>
  @import '../assets/css/_colors.scss';

  #contact {
    background-color: $red;
    padding: 5vh 0;

    h3 {
      padding-top: 5vh;
      color: $white;
      font-weight: bold;
    }

    h4 {
      color: $light_blue;
      font-weight: lighter;
    }

    h5 {
      padding-top: 5vh;
      color: $white;
    }
  }
</style>
