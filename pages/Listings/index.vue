<template>
  <div class="columns">
    <div class="column">
      <section class="section">
        <div class="container-fluid">
          <div class="columns">
            <div class="column is-12">
              <div class="columns">
                <div class="column">
                  <h1 class="title is-size-5">
                    <h1
                      class="title is-size-2 mb-5 is-font-weight-semibold"
                      style="font-weight: 700"
                    >
                      Listings 👋
                    </h1>
                  </h1>
                </div>

                <div class="column is-3">
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

              <div class="columns">
                <div class="column">
                  <!-- Main container -->
                  <nav class="level">
                    <!-- Left side -->
                    <div class="level-left">
                      <div class="level-item">
                        <div
                          style="
                            padding-bottom: 5px;
                            border-bottom: 3px solid #00d1b2;
                          "
                          class="mr-5 is-size-5"
                        >
                          <a style="color: #00d1b2; font-weight: 500"
                            >All Listings</a
                          >
                        </div>

                        <div style="padding-bottom: 5px" class="mx-5 is-size-5">
                          <a style="color: #cbcdd4; font-weight: 500"
                            >Top Selling</a
                          >
                        </div>
                        <div style="padding-bottom: 5px" class="mx-5 is-size-5">
                          <a style="color: #cbcdd4; font-weight: 500"
                            >Top Views</a
                          >
                        </div>
                        <div style="padding-bottom: 5px" class="mx-5 is-size-5">
                          <a style="color: #cbcdd4; font-weight: 500"
                            >Featured</a
                          >
                        </div>
                        <div style="padding-bottom: 5px" class="mx-5 is-size-5">
                          <a style="color: #cbcdd4; font-weight: 500">Sold</a>
                        </div>
                      </div>
                    </div>

                    <!-- Right side -->
                    <div class="level-right">
                      <div class="level-item">
                        <b-field>
                          <b-input
                            placeholder="Search..."
                            type="search"
                            icon="magnify"
                            expanded
                          >
                          </b-input>
                        </b-field>
                      </div>
                      <div class="level-item">
                        <b-button
                          style="float: right"
                          class="is-primary"
                          tag="router-link"
                          to="/Listings/New"
                        >
                          <span class="icon is-small"
                            ><i class="mdi mdi-plus"></i>
                          </span>
                        </b-button>
                      </div>
                    </div>
                  </nav>
                </div>
              </div>
            </div>
          </div>

          <div class="columns">
            <div class="column">
              <div
                class="card px-5 py-4 mb-5"
                v-for="listing in listings"
                :key="listing.index"
                style="border-radius: 12px"
              >
                <article class="media">
                  <figure class="media-left mr-5 pr-2">
                    <div class="box" style="padding: 0; margin: 0">
                      <b-tag
                        type="is-primary"
                        rounded
                        style="position: absolute; top: 20px; left: 30px"
                        ><b>Discounted</b></b-tag
                      >

                      <img
                        src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                        style="width: 250px; height: 150px; border-radius: 12px"
                      />
                    </div>
                  </figure>
                  <div class="media-content mt-2 my-auto">
                    <div class="columns">
                      <div class="column">
                        <b-dropdown aria-role="list" class="is-pulled-right">
                          <template #trigger="{ active }">
                            <b-button type="is-inverted is-ghost">
                              <i class="mdi mdi-24px mdi-dots-vertical"></i>
                            </b-button>
                          </template>

                          <b-dropdown-item aria-role="listitem">
                            <div class="media">
                              <b-icon
                                class="media-left"
                                icon="account-multiple"
                              ></b-icon>
                              <div class="media-content">
                                <h3>Mark as sold</h3>
                                <small>Only friends can see</small>
                              </div>
                            </div>
                          </b-dropdown-item>
                          <b-dropdown-item aria-role="listitem"
                            >Another action</b-dropdown-item
                          >
                          <b-dropdown-item aria-role="listitem"
                            >Something else</b-dropdown-item
                          >
                        </b-dropdown>

                        <h1
                          class="title is-size-4"
                          st
                          style="font-weight: 700; font-size: 1.5em; color: #"
                        >
                          {{ listing.listing_name }}
                        </h1>

                        <h2
                          class="subtitle is-size- pt-"
                          style="color: gray; font-size: 1em; font-weight: 400"
                        >
                          <i class="mdi mdi-18px mdi-map-marker-outline"></i>
                          {{ listing.listing_location }}
                        </h2>
                        <div class="columns mt-5 pt-">
                          <div class="column">
                            <nav class="level">
                              <!-- Left side -->
                              <div class="level-left">
                                <div class="level-item">
                                  <div class="columns">
                                    <div class="column">
                                      <span style="color: #9291a6">
                                        <span class="icon">
                                          <i
                                            class="mdi mdi-24px mdi-domain"
                                          ></i>
                                        </span>
                                        <p class="mr-5" style="font-weight: ">
                                          {{ listing.listing_type }}
                                        </p>
                                      </span>
                                    </div>
                                  </div>
                                </div>

                                <div class="level-item">
                                  <span style="color: #9291a6">
                                    <span class="icon">
                                      <i
                                        class="mdi mdi-24px mdi-bed-king-outline"
                                      ></i>
                                    </span>
                                    <p class="mr-5" style="font-weight: ">
                                      {{ listing.listing_bedroom }} Bedroom(s)
                                    </p>
                                  </span>
                                </div>

                                <div class="level-item">
                                  <span style="color: #9291a6">
                                    <span class="icon">
                                      <i class="mdi mdi-24px mdi-shower"></i>
                                    </span>
                                    <p class="mr-5" style="font-weight: ">
                                      {{ listing.listing_bathroom }} Bathroom(s)
                                    </p>
                                  </span>
                                </div>

                                <div class="level-item">
                                  <span style="color: #9291a6">
                                    <span class="icon">
                                      <i class="mdi mdi-24px mdi-chart-ppf"></i>
                                    </span>
                                    <p class="mr-5" style="font-weight: ">
                                      {{ listing.listing_land }} m2 Floor area
                                    </p>
                                  </span>
                                </div>
                              </div>

                              <!-- Right side -->
                              <div class="level-right">
                                <p class="level-item"></p>
                                <p
                                  class="title is-size-4"
                                  style="
                                    font-weight: 650;
                                    float: right;
                                    letter-spacing: -0.01em;
                                  "
                                >
                                  ₱ {{ listing.listing_price.toLocaleString() }}
                                </p>
                              </div>
                            </nav>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </article>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

    <div class="column is-3" style="">
      <div
        class="card"
        style="height: 100vh; position: fixed; overflow-y: auto"
      >
        <div class="column px-5" style="height: 100vh">
          <div class="columns">
            <div class="column">
              <div class="box" style="margin: 0; padding: 0">
                <img
                  src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                  style="width: 100%; border-radius: 12px"
                />
              </div>
            </div>
          </div>

          <div class="columns">
            <div class="column mt-2">
              <h1
                class="title is-size-4"
                st
                style="font-weight: 500; font-size: 1.5em; color: #"
              >
                Sea Residence by SMDC
              </h1>

              <h2
                class="subtitle is-size-6"
                style="color: gray; font-size: 1em; font-weight: 400"
              >
                Fairview, Quezon City, Metro Manila
              </h2>
            </div>
          </div>

          <div class="columns">
            <div class="column">
              <h2
                class="subtitle is-size-6"
                style="color: gray; font-size: 1em; font-weight: 400"
              >
                2 Bedrooms • 1 Bathroom • 100 Sqm
              </h2>
            </div>
          </div>

          <div class="columns">
            <div class="column">
              <h1
                class="title is-size-4"
                st
                style="font-weight: 500; font-size: 1.5em; color: #"
              >
                5,999,999.00
              </h1>

              <h2
                class="subtitle is-size-6"
                style="color: gray; font-size: 1em; font-weight: 400"
              >
                Price
              </h2>
            </div>
          </div>
          <div class="columns">
            <div class="column">
              <h1
                class="title is-size-4"
                st
                style="font-weight: 500; font-size: 1.5em; color: #"
              >
                Anjo Liwanag
              </h1>

              <h2
                class="subtitle is-size-6"
                style="color: gray; font-size: 1em; font-weight: 400"
              >
                Agent
              </h2>
            </div>
          </div>
          <div class="columns">
            <div class="column">
              <div class="mapouter">
                <div class="gmap_canvas">
                  <iframe
                    id="gmap_canvas"
                    src="https://maps.google.com/maps?q=trees%20residence&t=&z=13&ie=UTF8&iwloc=&output=embed"
                    frameborder="0"
                    scrolling="no"
                    marginheight="0"
                    marginwidth="0"
                    style="width: 100%; height: 200px"
                  ></iframe>
                </div>
              </div>
            </div>
          </div>
          <div class="columns">
            <div class="column">
              <span class="is-size-4">Photos</span>
            </div>
          </div>
          <div class="columns">
            <div class="column">
              <img
                class="is-rounded"
                src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                style="width: 100%; border-radius: 12px"
              />
            </div>

            <div class="column">
              <img
                class="is-rounded"
                src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                style="width: 100%; border-radius: 12px"
              />
            </div>

            <div class="column">
              <img
                class="is-rounded"
                src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                style="width: 100%; border-radius: 12px"
              />
            </div>
          </div>
          <div class="columns">
            <div class="column">
              <img
                class="is-rounded"
                src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                style="width: 100%; border-radius: 12px"
              />
            </div>

            <div class="column">
              <img
                class="is-rounded"
                src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                style="width: 100%; border-radius: 12px"
              />
            </div>

            <div class="column">
              <img
                class="is-rounded"
                src="https://www.homeguide.com.sg/wp-content/uploads/2020/02/home-guide-interior-design-renovations-8-keng-chin-rd-Living-room-dining.jpg"
                style="width: 100%; border-radius: 12px"
              />
            </div>
          </div>
          <div class="columns">
            <div class="column">
              <b-button class="is-primary" style="background: #00d1b2" expanded
                >Call Agent</b-button
              >
            </div>
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
      items: [1, 2, 3, 4, 5, 6],
      listings: [],
    }
  },
  mounted() {
    const self = this
    axios
      .get('http://localhost:6969/listings')
      .then(function (response) {
        // handle success
        // console.log(response.data)
        self.listings = response.data
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
