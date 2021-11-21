<template>
  <div>
    <div class="columns px-5">
      <div class="column is-9">
        <div class="container-fluid">
          <div class="column is-12">
            <nav class="level">
              <!-- Left side -->
              <div class="level-left">
                <div class="level-item">
                  <p class="subtitle is-5">
                    <i class="mdi mdi-menu mdi-36px"></i>
                  </p>
                </div>
                <div class="level-item">
                  <span
                    class="title is-size-3 is-font-weight-semibold"
                    style="font-weight: 700"
                  >
                    Projects
                  </span>
                </div>
              </div>

              <!-- Right side -->
              <div class="level-right">
                <div class="level-item py-2">
                  <article class="media ml-5" style="float: right">
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
            </nav>
          </div>

          <div class="column">
            <div class="columns">
              <div class="column">
                <nav class="level">
                  <!-- Left side -->
                  <div class="level-left">
                    <div class="level-item">
                      <b-field class="is-5" style="width: 500px">
                        <b-input
                          placeholder="Search"
                          type="search"
                          icon-pack="mdi"
                          icon="magnify"
                          width="500"
                          expanded
                        >
                        </b-input>
                      </b-field>
                    </div>
                  </div>

                  <!-- Right side -->
                  <div class="level-right">
                    <div class="level-item">
                      <b-dropdown aria-role="list">
                        <template #trigger="{ active }">
                          <b-button
                            label="Filter by"
                            type="is-primary"
                            :icon-right="active ? 'menu-up' : 'menu-down'"
                            outlined
                          />
                        </template>

                        <b-dropdown-item aria-role="listitem"
                          >Action</b-dropdown-item
                        >
                        <b-dropdown-item aria-role="listitem"
                          >Another action</b-dropdown-item
                        >
                        <b-dropdown-item aria-role="listitem"
                          >Something else</b-dropdown-item
                        >
                      </b-dropdown>
                    </div>
                    <div class="level-item">
                      <b-dropdown aria-role="list">
                        <template #trigger="{ active }">
                          <b-button
                            label="Sort by"
                            type="is-primary"
                            :icon-right="active ? 'menu-up' : 'menu-down'"
                            outlined
                          />
                        </template>

                        <b-dropdown-item aria-role="listitem"
                          >Action</b-dropdown-item
                        >
                        <b-dropdown-item aria-role="listitem"
                          >Another action</b-dropdown-item
                        >
                        <b-dropdown-item aria-role="listitem"
                          >Something else</b-dropdown-item
                        >
                      </b-dropdown>
                    </div>

                    <b-dropdown aria-role="list">
                      <template #trigger="{ active }">
                        <b-button
                          label="New"
                          type="is-primary"
                          :icon-right="active ? 'menu-up' : 'plus'"
                        />
                      </template>

                      <b-dropdown-item
                        aria-role="listitem"
                        @click="modalNewProject = true"
                        >New Project</b-dropdown-item
                      >
                      <b-dropdown-item aria-role="listitem"
                        >Export List</b-dropdown-item
                      >
                      <b-dropdown-item aria-role="listitem"
                        >Export Report</b-dropdown-item
                      >
                    </b-dropdown>
                  </div>
                </nav>
              </div>
            </div>

            <div class="">
              <b-table
                class="card"
                :data="projects"
                :paginated="isPaginated"
                :per-page="perPage"
                :current-page.sync="currentPage"
                :pagination-simple="isPaginationSimple"
                :pagination-position="paginationPosition"
                :default-sort-direction="defaultSortDirection"
                :pagination-rounded="isPaginationRounded"
                :sort-icon="sortIcon"
                :sort-icon-size="sortIconSize"
                default-sort="developer_name"
                aria-next-label="Next page"
                aria-previous-label="Previous page"
                aria-page-label="Page"
                aria-current-label="Current page"
              >
                <b-table-column
                  label="Logo"
                  width="120"
                  sortable
                  v-slot="props"
                >
                  <div class="">
                    <img
                      src="https://pbs.twimg.com/profile_images/1182115674954461185/lMd5BLTr.jpg"
                      style="width: 100%"
                    />
                  </div>
                </b-table-column>

                <b-table-column label="Project name" sortable v-slot="props">
                  <div class="py-5">
                    <article class="media">
                      <div class="media-content">
                        <div class="content">
                          <p>
                            <strong>
                              {{ props.row.project_name }}
                            </strong>
                            <br />
                            <small>
                              {{ props.row.developer_name }}
                            </small>
                          </p>
                        </div>
                      </div>
                    </article>
                  </div>
                </b-table-column>

                <b-table-column
                  label="Projects"
                  class="py-5"
                  sortable
                  v-slot="props"
                  numeric
                >
                  <div class="py-5">
                    <span class="has-text-weight-semibold"> 1,568 </span>
                  </div>
                </b-table-column>

                <b-table-column
                  label="Listings"
                  class="my-5"
                  sortable
                  v-slot="props"
                  numeric
                >
                  <div class="py-5">
                    <span class="has-text-weight-semibold"> 1,568 </span>
                  </div>
                </b-table-column>

                <b-table-column
                  label="Views"
                  class="my-5"
                  sortable
                  v-slot="props"
                  numeric
                >
                  <div class="py-5">
                    <span class="has-text-weight-semibold"> 1,568 </span>
                  </div>
                </b-table-column>

                <b-table-column
                  label=""
                  class="my-5"
                  sortable
                  v-slot="props"
                  numeric
                >
                  <div class="py-5">
                    <i class="mdi mdi-dots-vertical"></i>
                  </div>
                </b-table-column>
              </b-table>
            </div>
          </div>
        </div>
      </div>

      <div class="column card" style="height: 100vh; overflow-y: auto">
        <div class="columns px-2 pt-4">
          <div class="column">
            <span class="is-size-4 has-text-weight-bold" style="color: #00947e"
              >Projects Statistics</span
            >
            <p>Top develops</p>
          </div>
        </div>

        <!-- <div class="columns">
          <div class="column  mx-5" style="background: #E3F8E9; color: #00947E">
            <div class="columns">
              <div class="column">
                <p class="is-size-5" style="font-weight: 500">
                  Total Properties
                </p>
                <small>Lorem ipsum dolor sit </small>
              </div>
              <div class="column is-3">
                <span class="is-size-3" style="font-weight: 600">759</span>
              </div>
            </div>
          </div>
        </div> -->

        <div class="columns mt-2" style="" v-for="item in items">
          <div
            class="column mx-5 px- py-4"
            style="background: #e3f8e9; color: #009178; border-radius: 12px"
          >
            <div class="columns">
              <div class="column is-3 has-text-centered">
                <span class="is-size-3" style="font-weight: 700">759</span>
              </div>
              <div class="column">
                <p class="is-size-5" style="font-weight: 500">
                  Total Properties
                </p>
                <small>Lorem ipsum dolor sit </small>
              </div>
            </div>
          </div>
        </div>

        <!-- <div class="columns mt-2">
          <div class="column card mx-5" style="background: #E3F8E9; color: #00947E">
            <span class="is-size-2" style="font-weight: 600">89</span>
            <p class="">Properties for sale</p>
          </div>
        </div> -->

        <div class="columns px-2 pt-4">
          <div class="column">
            <span class="is-size-4 has-text-weight-bold text"
              >Top Grossing Projects</span
            >
            <p>Top develops</p>
          </div>
        </div>
        <div
          class="px-1 mt-2 mx-2 py-3 columns"
          v-for="item in developers"
          :key="item.index"
          style="border: 1px solid #e3e3e3"
        >
          <div class="columns px-1 py-1">
            <div class="column">
              <article class="media">
                <figure class="media-left">
                  <p class="image is-48x48">
                    <img
                      src="https://bulma.io/images/placeholders/128x128.png"
                      class="is-rounded"
                    />
                  </p>
                </figure>
                <div class="media-content">
                  <div class="content">
                    <strong class="">{{ item.developer_name }}</strong>
                    <br />
                    <small class=""
                      ><strong class=""></strong> ₱ 895,056.00</small
                    >
                  </div>
                </div>
              </article>
            </div>
          </div>
        </div>
      </div>
    </div>
    <b-modal v-model="modalNewProject" :width="1080" scroll="keep">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
            <span>Create Project</span>
          </p>
          <button
            class="card-header-icon"
            aria-label="more options"
            @click="modalNewProject = false"
          >
            <span class="icon">
              <i class="mdi mdi-close" aria-hidden="true"></i>
            </span>
          </button>
        </header>
        <div class="columns" style="">
          <div class="column" style="margin: 0; padding: 0">
            <img
              src="https://static-ph.lamudi.com/static/media/d2F0ZXJtYXJrL2xhbXVkaTpib3R0b20tbGVmdDowLjE%3D/2x2x5x1280x500/144ae16fac72e9.jpg"
              alt=""
            />
          </div>
        </div>
        <div class="columns">
          <div class="column">
            <div class="card px-5 py-5 mx-5" style="margin-top: -50px">
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
                    <b-field label="Project name" expanded>
                      <b-input
                        placeholder="Project name"
                        v-model="project_name"
                      ></b-input>
                    </b-field>

                    <b-field label="Contact no.">
                      <b-input
                        placeholder="Developer name"
                        v-model="project_contact"
                      ></b-input>
                    </b-field>
                  </b-field>

                  <b-field label="Location">
                    <b-input
                      placeholder="Project location"
                      v-model="project_location"
                    ></b-input>
                  </b-field>

                  <b-field label="Website">
                    <b-input
                      placeholder="Developer name"
                      v-model="project_website"
                    ></b-input>
                  </b-field>

                  <b-field label="Project type">
                    <b-input
                      placeholder="Developer name"
                      v-model="project_type"
                    ></b-input>
                  </b-field>

                  <b-field label="Description">
                    <b-input
                      type="textarea"
                      v-model="project_description"
                    ></b-input>
                  </b-field>
                </div>
              </div>
            </div>

            <div class="columns">
              <div class="column">
                <b-button @click="createProject()">Create project</b-button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </b-modal>

    <b-modal
      v-model="modalViewProject"
      :width="modalViewWidth"
      :height="modalViewHeight"
      scroll="keep"
    >
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
            <span>Create Project</span>
          </p>
          <button
            class="card-header-icon"
            aria-label="more options"
            @click="modalViewProject = false"
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
                    value="Kevin Garvey"
                  ></b-input>
                </b-field>

                <b-field label="Contact no.">
                  <b-input
                    placeholder="Developer name"
                    value="Kevin Garvey"
                  ></b-input>
                </b-field>
              </b-field>

              <b-field label="Address">
                <b-input
                  placeholder="Developer name"
                  value="Kevin Garvey"
                ></b-input>
              </b-field>

              <b-field label="Website">
                <b-input
                  placeholder="Developer name"
                  value="Kevin Garvey"
                ></b-input>
              </b-field>

              <b-field label="Description">
                <b-input type="textarea"></b-input>
              </b-field>
            </div>
          </div>
        </div>

        <footer class="card-footer px-5 py-5">
          <b-button
            href="#"
            class="card-footer-item is-primary"
            @click="createProject()"
            >Create Project</b-button
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
      modalNewProject: false,
      modalViewProject: false,
      modalViewHeight: '100vh',
      modalViewWidth: '90vw',
      masd: 'height: 90vh;width: 90vw;',
      labelPosition: 'on-border',

      projects: [],

      project_name: '',
      project_contact: '',
      project_location: '',
      project_website: '',
      project_type: '',
      project_description: '',
    }
  },
  methods: {
    createProject() {
      const self = this
      axios
        .post('http://localhost:6969/projects', {
          project_name: self.project_name,
          project_contact: self.project_contact,
          project_location: self.project_location,
          project_website: self.project_website,
          project_type: self.project_type,
          project_description: self.project_description,
        })
        .then(function (response) {
          console.log(response)
          self.modalNewProject = false
        })
        .catch(function (error) {
          console.log(error)
          self.modalNewProject = false
        })
    },
  },
  mounted() {
    const self = this
    axios
      .get('http://localhost:6969/projects')
      .then(function (response) {
        // handle success
        // console.log(response.data)
        self.projects = response.data
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
