<template>
  <div>
    <div class="columns">
      <div class="column is-2" style="background: white; height: 100vh">
        <div class="columns">
          <div class="column px-5 py-5">
            <b-button icon-left="chevron-left"  class="mr-3"></b-button>
            <span class="is-size-4 has-text-weight-bold">Mailbox</span>
          </div>
        </div>
        <div class="columns px-2">
          <div class="column">
            <b-button
              size="is-medium is-primary is-"
              icon-left="mail"
              expanded
            >
              New Message
            </b-button>
          </div>
        </div>

        <div class="columns">
          <div class="column">
            <div class="columns">
              <div class="column sidebar2">
                <NuxtLink
                  :to="item.route"
                  class="my-3 sidenav2"
                  style="font-weight: 500"
                  v-for="item in items"
                  :key="item.title"
                >
                  <span class="icon-text">
                    <span class="icon">
                      <i :class="item.icon"></i>
                    </span>
                    <span class="ml-3">{{ item.title }}</span>
                  </span>
                </NuxtLink>
              </div>
            </div>

            <div class="columns">
              <div class="column sidebar2">
                <h3 class="is-size-5 px-5 has-text-grey">Tags</h3>
              </div>
            </div>

            <div class="columns">
              <div class="column sidebar2">
                <NuxtLink
                  :to="item.route"
                  class="my-3 sidenav2"
                  style="font-weight: 500"
                  v-for="item in items2"
                  :key="item.title"
                >
                  <span class="icon-text">
                    <span class="icon">
                      <i :class="item.icon"></i>
                    </span>
                    <span class="ml-3">{{ item.title }}</span>
                  </span>
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="column is-3 py-5" style="background: #f4f6f8">
        <div class="columns">
          <div class="column">
            <b-field>
              <b-input placeholder="Search" v-model="name"></b-input>
            </b-field>
          </div>
        </div>

        <div class="columns is-multiline px-4 pb-5">
          <div
            class="column is-12 avatar py-5"
            v-for="item in items"
            :key="item.index"
          >
            <article class="media">
              <figure class="media-left">
                <p class="image is-48x48">
                  <img
                    class="is-rounded"
                    src="https://bulma.io/images/placeholders/128x128.png"
                  />
                </p>
              </figure>
              <div class="media-content">
                <div class="content">
                  <small class="is-pulled-right">11:11</small>
                  <p>
                    <strong class="has-text-weight-semibold"
                      >Adrian Van Ladrillano</strong
                    >
                    <br />
                    Lorem ipsum, dol conssicing elit...
                  </p>
                </div>
              </div>
            </article>
          </div>
        </div>
        
      </div>

      <div class="column px-5 py-5" style="background: white">
        <div class="columns pt-3">
          <div class="column">
            <nav class="level">
              <!-- Left side -->
              <div class="level-left">
                <div class="level-item">
                  <b-tag
                    type="is-primary"
                    closable
                    aria-close-label="Close tag"
                    size="is-large"
                  >
                    Possible buyer
                  </b-tag>
                </div>
              </div>

              <!-- Right side -->
              <div class="level-right">
                <p class="level-item ml-5">
                  <i class="mdi mdi-24px mdi-star"></i>
                </p>
                <p class="level-item ml-5">
                  <i class="mdi mdi-24px mdi-printer"></i>
                </p>
                <p class="level-item ml-5">
                  <i class="mdi mdi-24px mdi-trash-can"></i>
                </p>
                <p class="level-item ml-5">
                  <i class="mdi mdi-24px mdi-dots-vertical"></i>
                </p>
              </div>
            </nav>
          </div>
        </div>
        <div class="columns">
          <div class="column">
            <p class="has-text-grey">Today, April 4, 2021, 11:59 PM</p>
            <span class="is-size-3 has-text-weight-semibold">Subject here</span>
          </div>
        </div>

        <div class="columns">
          <div class="column">
            <article class="media">
              <figure class="media-left">
                <p class="image is-48x48">
                  <img
                    class="is-rounded"
                    src="https://bulma.io/images/placeholders/128x128.png"
                  />
                </p>
              </figure>
              <div class="media-content">
                <div class="content">
                  <small class="is-pulled-right">11:11</small>
                  <p>
                    <strong class="has-text-weight-semibold"
                      >Adrian Van Ladrillano</strong
                    >
                    <br />
                    Lorem ipsum, dol conssicing elit...
                  </p>
                </div>
              </div>
            </article>
          </div>
        </div>

        <div class="columns">
          <div class="column">
            <p>Hey Adrian Van,</p>
            <br />
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Corrupti
              voluptates ipsum iste eveniet qui deleniti maiores quasi?
              Repellendus neque praesentium natus. Ipsa placeat voluptatibus
              quaerat culpa exercitationem tempora architecto adipisci?
              <a href="">https://www.loremipsumdolorsit.com/start</a>
            </p>
            <br />
            <p>Regards,</p>
            <p>Ajay-ann,</p>
          </div>
        </div>

        <div class="columns mt-5">
          <div class="column">
            <b-field>
              <b-input maxlength="200" type="textarea"></b-input>
            </b-field>
          </div>
        </div>
        <div class="columns">
          <div class="column">
            <b-button
              class="is-pulled-right px-5 is-primary"
              icon-right="send-outline"
              >Send</b-button
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from '~/components/Card'
import axios from 'axios'

export default {
  name: 'HomePage',

  components: {
    Card,
  },
  data() {
    return {
      items: [
        {
          title: 'Inbox',
          icon: 'mdi mdi-24px	 mdi-inbox-arrow-down-outline mr-5',
          route: '/',
        },
        {
          title: 'Spam',
          icon: 'mdi mdi-24px	 mdi-alert-circle-outline mr-5',
          route: '/Listings',
        },
        {
          title: 'Important',
          icon: 'mdi mdi-24px	 mdi-star-outline mr-5',
          route: '/Developers',
        },
        {
          title: 'Deleted',
          icon: 'mdi mdi-24px	 mdi-trash-can-outline mr-5',
          route: '/Projects',
        },
      ],
      items2: [
        {
          title: 'Something',
          icon: 'mdi mdi-24px mdi-label mr-5',
          route: '/',
        },
        {
          title: 'Something 2',
          icon: 'mdi mdi-24px mdi-label mr-5',
          route: '/Listings',
        },
        {
          title: ' Something 3',
          icon: 'mdi mdi-24px mdi-label mr-5',
          route: '/Developers',
        },
        {
          title: 'Something 4',
          icon: 'mdi mdi-24px mdi-label mr-5',
          route: '/Projects',
        },
        {
          title: 'Something 5',
          icon: 'mdi mdi-24px mdi-label mr-5',
          route: '/Projects',
        },
      ],
      modalNewDeveloper: false,
      modalViewDeveloper: false,
      modalViewHeight: '100vh',
      modalViewWidth: '90vw',
      masd: 'height: 90vh;width: 90vw;',
      labelPosition: 'on-border',

      //   Inputs
      developer_name: '',
      developer_description: '',
      developer_address: '',
      developer_website: '',
      developer_contact: '',

      //   arrays
      developers: [],
    }
  },
  methods: {
    createDeveloper() {
      const self = this
      axios
        .post('http://localhost:6969/developers', {
          developer_name: self.developer_name,
          developer_description: self.developer_description,
          developer_address: self.developer_address,
          developer_website: self.developer_website,
          developer_contact: self.developer_contact,
        })
        .then(function (response) {
          console.log(response)
          self.modalNewDeveloper = false
        })
        .catch(function (error) {
          console.log(error)
          self.modalNewDeveloper = false
        })
    },
  },
  mounted() {
    const self = this
    axios
      .get('http://localhost:6969/developers')
      .then(function (response) {
        // handle success
        // console.log(response.data)
        self.developers = response.data
        console.log(this.listings)
      })
      .catch(function (error) {
        // handle error
        console.log(error)
      })
      .then(function () {
        // always executed
      })
  },
}
</script>
<style>
.sidebar2 {
  margin: 0;
  padding: 0;
}
.mapouter {
}
.gmap_canvas {
}
a.sidenav2 {
  display: block;
  padding-top: 8px;
  padding-left: ;
  padding-right: ;
  padding-bottom: 8px;
  color: gray;
  text-decoration: none;
  margin-left: 2.5em;
  margin-right: auto;
}

a.sidenav2.active {
  background-color: white;
  color: white;
}

.avatar:hover {
  background-color: white;
  border-radius: 12px;
}
.sidebar2 a:hover {
  background-color: white;
  color: #00d1b2;
  font-weight: 700;
}
</style>
