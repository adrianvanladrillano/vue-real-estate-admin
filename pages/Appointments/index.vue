<template>
  <div>
    <div class="columns">
      <div class="column">
        <section class="section">
          <div class="container-fluid">
            <div class="columns">
              <div class="column is-12">
                <div class="columns">
                  <div class="column">
                    <h1 class="title is-size-5">
                      Hi Adrian,
                      <h1
                        class="title is-size-2 is-font-weight-semibold"
                        style="font-weight: 700"
                      >
                        Appointments 👋
                      </h1>
                    </h1>
                  </div>
                  <div class="column">
                    <article class="media ml-5" style="float: right">
                      <figure class="media-left">
                        <p class="image is-64x64">
                          <img
                            class="is-rounded"
                            src="https://bulma.io/images/placeholders/128x128.png"
                          />
                        </p>
                      </figure>
                      <div class="media-content">
                        <div class="content">
                          <p>
                            <strong>Adrian Van Ladrillano</strong>
                            <br />
                            Developer
                          </p>
                        </div>
                      </div>
                    </article>
                  </div>
                </div>
              </div>
            </div>

            <div class="columns mt-5">
              <div class="column">
                <div class="columns">
                  <div class="column is-5">
                    <div class="columns">
                      <div
                        class="column card is-4 mr-4 px-5"
                        style="
                          background: white;
                          margin-bottom: 0;
                          border-top-right-radius: 12px;
                          border-top-left-radius: 12px;
                          border-bottom-right-radius: 0;
                          border-bottom-left-radius: 0;
                        "
                      >
                        <span class="has-text-weight-semibold">Today</span>
                        <h1 class="is-size-5">
                          6 <small style="font-size: 0.7em">appointments</small>
                        </h1>
                      </div>
                      <div
                        class="column card is-4 mr-4 px-5"
                        style="
                          background: #00d1b2;
                          color: white;
                          border-top-right-radius: 12px;
                          border-top-left-radius: 12px;
                          border-bottom-right-radius: 0;
                          border-bottom-left-radius: 0;
                        "
                      >
                        <span class="has-text-weight-semibold">Tomorrow</span>
                        <h1 class="is-size-5">
                          6 <small style="font-size: 0.7em">appointments</small>
                        </h1>
                      </div>
                      <div
                        class="column card is-4 mr-5 px-5"
                        style="
                          background: #00d1b2;
                          color: white;
                          border-top-right-radius: 12px;
                          border-top-left-radius: 12px;
                          border-bottom-right-radius: 0;
                          border-bottom-left-radius: 0;
                        "
                      >
                        <span class="has-text-weight-semibold is-size-6"
                          >All</span
                        >
                        <h1 class="is-size-5">
                          6 <small style="font-size: 0.7em">appointments</small>
                        </h1>
                      </div>
                    </div>
                  </div>

                  <div class="column is-">
                    <div class="columns">
                      <div class="column">
                        <b-field grouped class="is-pulled-right">
                             <b-field>
                                <b-select placeholder="All Statuses">
                                    <option
                                        v-for="option in data"
                                        :value="option.id"
                                        :key="option.id">
                                        {{ option.user.first_name }}
                                    </option>
                                </b-select>
                            </b-field>
                            <b-field>
                              <b-datepicker
                                placeholder="Click to select..."
                                v-model="dates"
                                range
                                expanded
                              >
                              </b-datepicker>
                              <p class="control">
                              <b-button
                                type="is-primary"
                                icon-right="calendar"
                                label=""
                              />
                            </p>
                            </b-field>
                            
                          </b-field>
                        </b-field>
                      </div>
                    </div>
                    
                  </div>
                </div>

                <div class="columns">
                  <div class="column" style="margin: 0; padding: 0">
                    <div
                      class="card pt-5 px-2"
                      @click="modalViewDeveloper = true"
                      style="background: white"
                    >
                      <b-table
                        :data="isEmpty ? [] : developers"
                        :bordered="isBordered"
                        :striped="isStriped"
                        :narrowed="isNarrowed"
                        :hoverable="isHoverable"
                        :loading="isLoading"
                        :focusable="isFocusable"
                        :mobile-cards="hasMobileCards"
                      >
                        <b-table-column
                          field="last_name"
                          label="Property"
                          :td-attrs="columnTdAttrs"
                          v-slot="props"
                        >
                          <article class="media">
                            <figure class="media-left">
                              <p class="image is-64x64 px-2 py-2">
                                <img
                                  src="https://cf.bstatic.com/images/hotel/max500/179/179484958.jpg"
                                  alt=""
                                  class="is-rounded"
                                />
                              </p>
                            </figure>
                            <div class="media-content">
                              <div class="content">
                                <p>
                                  <strong>Ayala homes</strong>
                                  <br />
                                  <small>Anjo Liwanag</small>
                                </p>
                              </div>
                            </div>
                          </article>

                          {{ props.row.last_name }}
                        </b-table-column>

                        <b-table-column
                          field="id"
                          label="Client"
                          :td-attrs="columnTdAttrs"
                          v-slot="props"
                        >
                          <span class="is-size-6 has-text-weight-semibold">
                            Adrian Van Ladrillano
                          </span>
                          <br />
                          <small class="">Somthing here.</small>
                          {{ props.row.id }}
                        </b-table-column>

                        <b-table-column
                          field="first_name"
                          label="Contact"
                          :td-attrs="columnTdAttrs"
                          v-slot="props"
                        >
                          <div style="margin-top: auto; margin-bottom: auto">
                            <strong
                              class="has-font-weight-semibold has-text-grey"
                              >(+63)
                              <span class="has-text-grey"> 9959005870</span>
                            </strong>
                          </div>

                          {{ props.row.first_name }}
                        </b-table-column>

                        <b-table-column
                          field="last_name"
                          label="Appointment"
                          :td-attrs="columnTdAttrs"
                          v-slot="props"
                        >
                          <span class="is-size-6 has-text-weight-semibold">
                            April, 14 2021
                          </span>
                          <br />
                          <small class="">Morning</small>
                          {{ props.row.last_name }}
                        </b-table-column>

                        <b-table-column
                          field="Status"
                          label="Status"
                          :th-attrs="dateThAttrs"
                          :td-attrs="columnTdAttrs"
                          centered
                          v-slot="props"
                        >
                          <span class="tag is-success">
                            {{ new Date(props.row.date).toLocaleDateString() }}
                          </span>
                        </b-table-column>

                        <b-table-column
                          label="Action"
                          :td-attrs="columnTdAttrs"
                          v-slot="props"
                        >
                          <span>
                            <b-icon
                              v-if="props.row.id !== 'Total'"
                              pack="fas"
                              :icon="
                                props.row.gender === 'Male' ? 'mars' : 'venus'
                              "
                            >
                            </b-icon>
                            {{ props.row.gender }}
                          </span>
                        </b-table-column>

                        <template #empty>
                          <div class="has-text-centered">No records</div>
                        </template>
                      </b-table>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
    <b-modal v-model="modalNewDeveloper" :width="1080" scroll="keep">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
            <span>Create Developer</span>
          </p>
          <button
            class="card-header-icon"
            aria-label="more options"
            @click="modalNewDeveloper = false"
          >
            <span class="icon">
              <i class="mdi mdi-close" aria-hidden="true"></i>
            </span>
          </button>
        </header>
        <div class="card-content">
          <div class="columns">
            <div class="column is-4">
              <img
                src="https://bulma.io/images/placeholders/128x128.png"
                style="width: 500px"
                alt=""
              />

              <input type="file" name="" />
            </div>

            <div class="column">
              <b-field grouped>
                <b-field label="Developer name" expanded>
                  <b-input
                    placeholder="Developer name"
                    v-model="developer_name"
                  ></b-input>
                </b-field>

                <b-field label="Contact no.">
                  <b-input
                    placeholder="Developer name"
                    v-model="developer_contact"
                  ></b-input>
                </b-field>
              </b-field>

              <b-field label="Address">
                <b-input
                  placeholder="Developer name"
                  v-model="developer_address"
                ></b-input>
              </b-field>

              <b-field label="Website">
                <b-input
                  placeholder="Developer name"
                  v-model="developer_website"
                ></b-input>
              </b-field>

              <b-field label="Description">
                <b-input
                  type="textarea"
                  v-model="developer_description"
                ></b-input>
              </b-field>
            </div>
          </div>
        </div>

        <footer class="card-footer px-5 py-5">
          <b-button
            href="#"
            class="card-footer-item is-primary"
            @click="createDeveloper()"
            >Create Developer</b-button
          >
        </footer>
      </div>
    </b-modal>

    <b-modal
      v-model="modalViewDeveloper"
      :width="modalViewWidth"
      :height="modalViewHeight"
      scroll="keep"
    >
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
            <span>View Developer</span>
          </p>
          <button
            class="card-header-icon"
            aria-label="more options"
            @click="modalNewDeveloper = false"
          >
            <span class="icon">
              <i class="mdi mdi-close" aria-hidden="true"></i>
            </span>
          </button>
        </header>
        <div class="card-content">
          <div class="columns">
            <div class="column">
              Lorem ipsum dolor, sit amet consectetur adipisicing elit. Expedita
              impedit aliquam, recusandae illum maiores blanditiis voluptatibus
              sit natus totam commodi, earum nisi ad! Officia, esse similique
              quod consequatur perferendis delectus!
            </div>
          </div>
        </div>

        <footer class="card-footer px-5 py-5">
          <b-button
            href="#"
            class="card-footer-item is-primary"
            @click="createDeveloper()"
            >Create Developer</b-button
          >
        </footer>
      </div>
    </b-modal>
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
      items: [1, 2, 3, 4, 5, 6],
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
