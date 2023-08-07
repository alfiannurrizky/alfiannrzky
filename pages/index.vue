<template>
  <div>
    <section id="home">
      <b-row style="margin-left: 0; margin-right: 0">
        <b-col md="4">
          <b-img src="alv.png" id="avatar-img" fluid alt="Responsive image" />
        </b-col>

        <b-col md="8">
          <h2
            class="intro animate__animated animate__fadeInUp animate__fast"
            id="typed-text"
          >
            Hi There👋,
            <br />I<span>'m Alfian&nbsp;Nurrizky</span>.
          </h2>

          <div class="col-md-10 info">
            A <b> Software Developer</b> and interested in back-end engineering
            .<br />
            I am skilled with building web application based on RESTful API,
            <br />

            <div
              class="social-icons animate__animated animate__fadeInUp animate__delay-1s"
            >
              <social-link :to="socialLinks.github">
                <GithubIcon />
              </social-link>

              <social-link :to="socialLinks.linkedin">
                <LinkedinIcon />
              </social-link>

              <social-link :to="socialLinks.mail">
                <MailIcon />
              </social-link>
            </div>
          </div>
        </b-col>
      </b-row>
    </section>

    <section id="about">
      <div class="container animate__animated animate__fadeIn">
        <div class="row">
          <div class="col-md-6">
            <div class="about">
              <h1 class="line-after">About Me</h1>
              <p>
                My name is Alfian Nurrizky, I'm interested in web development
                especially in <b>back-end engineering</b> and
                <b>
                  I am currently an informatics engineering student at
                  <u>Pamulang University</u></b
                >.
              </p>
              <h4 class="mt-5">Tech Stacks</h4>
              <p>This is the technology i usually use:</p>
              <div class="row animate__animated animate__fadeInUp">
                <div class="col">
                  <ul style="list-style-type: circle">
                    <li>HTML & CS</li>
                    <li>Node.js (Express Framework)</li>
                    <li>PHP (Laravel Framework)</li>
                  </ul>
                </div>
                <div class="col">
                  <ul style="list-style-type: circle">
                    <li>JavaScript</li>
                    <li>Vue.js</li>
                    <li>Typescript</li>
                  </ul>
                </div>
                <div class="col">
                  <ul style="list-style-type: circle">
                    <li>Postman</li>
                    <li>Docker</li>
                    <li>Git</li>
                    <li>Mysql</li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-6">
            <img
              src="@/assets/code.jpg"
              alt="About Illustration"
              class="abt-img"
            />
          </div>
        </div>
      </div>
    </section>

    <section id="projects" data-aos="zoom-in">
      <div
        class="about page animate__animated animate__fadeIn"
        style="margin-top: 200px"
      >
        <h2>My Projects</h2>
        <div class="container">
          <div class="row" v-for="(project, index) in projects" :key="index">
            <div class="col-md-5">
              <img
                :src="project.image_cover"
                :alt="project.title"
                class="project-cover"
              />
            </div>
            <div class="col-md-5">
              <h2 class="mt-3" style="text-align: left">
                {{ project.title }}
                <hr class="dope" />
              </h2>
              <b-card class="cardss">
                <p>{{ project.description }}</p>
                <hr />
                <b-link :href="project.github_url"
                  >View source code <GithubIcon style="color: #000"
                /></b-link>
              </b-card>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" data-aos="fade-down">
      <b-container class="page animate__animated animate__fadeIn">
        <b-row class="justify-content-center">
          <b-col cols="md-6">
            <h2 class="title">Contact Me</h2>

            <b-form class="mb-5" @submit.prevent="sendMessage">
              <b-form-group id="input-group-1" label="Your Name:">
                <b-form-input v-model="formData.name" required></b-form-input>
              </b-form-group>

              <b-form-group id="input-group-2" label="Your Email:">
                <b-form-input
                  v-model="formData.email"
                  type="email"
                  required
                ></b-form-input>
              </b-form-group>

              <b-form-group id="input-group-3" label="Your Message">
                <b-form-textarea
                  v-model="formData.message"
                  no-resize
                  rows="3"
                  required
                ></b-form-textarea>
              </b-form-group>

              <b-button type="submit" variant="success">Submit</b-button>
            </b-form>
          </b-col>
        </b-row>
      </b-container>
    </section>
  </div>
</template>

<script>
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import LinkedinIcon from "vue-ionicons/dist/logo-linkedin.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";

export default {
  components: {
    GithubIcon,
    LinkedinIcon,
    MailIcon,
  },

  data() {
    return {
      avatar: require("@/assets/avatar-1.webp"),
      socialLinks: {
        github: "https://github.com/alfiannurrizky",
        linkedin: "https://www.linkedin.com/in/alfian-nurrizky/",
        mail: "mailto:alfiannrzky0@gmail.com",
      },
      formData: {
        name: "",
        email: "",
        message: "",
      },
      projects: [
        {
          title: "E-wallet Services",
          description:
            "Create E-wallet services RESTful API, and has several features",
          image_cover: require("@/assets/ewallet.jpg"),
          github_url: "https://github.com/alfiannurrizky/e-wallet-services",
        },
        {
          title: "Point of Sales RESTful API",
          description: "Point of Sales services for handle product purchase",
          image_cover: require("@/assets/pos.jpg"),
          github_url:
            "https://github.com/alfiannurrizky/point-of-sales-service",
        },
        {
          title: "Seminar Events",
          description: "website application to notify seminar info to students",
          image_cover: require("@/assets/seminar.jpg"),
          github_url: "https://github.com/alfiannurrizky/seminar-events",
        },
        {
          title: "Whatsapp Bot",
          description:
            "whatsapp bot for check adhan times using several packages",
          image_cover: require("@/assets/bot.jpg"),
          github_url: "https://github.com/alfiannurrizky/whatsapp-bot",
        },
      ],
    };
  },
  methods: {
    async sendMessage(e) {
      const self = this;
      var data = new FormData();

      data.append("Name", self.formData.name);
      data.append("Email", self.formData.email);
      data.append("Message", self.formData.message);

      fetch("https://formspree.io/f/xrgweqwa", {
        method: "POST",
        body: data,
        headers: {
          Accept: "application/json",
        },
      }).then((response) => {
        if (response.ok) {
          alert("success");
          // form.reset();
        } else {
          alert("Sending message failed, please try again");
        }
      });
    },
  },
};
</script>
<style scoped>
.container {
  margin-top: 140px;
  text-align: left;
}
.line-after {
  overflow: hidden;
}

section {
  padding-top: 20px;
}

.line-after::after {
  content: "";
  display: inline-block;
  height: 0.5em;
  vertical-align: bottom;
  width: 100%;
  margin-right: -100%;
  margin-left: 10px;
  border-top: 2px solid rgb(187, 179, 179);
}
.abt-img {
  width: 500px;
  height: 480px;
  border-radius: 5px;
}

.row {
  margin-top: 70px;
}

.project-cover {
  width: 400px;
  border-radius: 3px;
  margin-top: 30px;
}

.container {
  margin-top: 120px;
}
form {
  margin-top: 40px;
  text-align: left;
}

.title {
  text-align: center;
}

.cardss {
  margin-top: 3px;
  background: #44a08d;
  background: -webkit-linear-gradient(to right, #093637, #44a08d);
  background: linear-gradient(to right, #010c0c, #44a08d);
  /* mt-3 mb-3 text-left text-dark background-color */
}
</style>
