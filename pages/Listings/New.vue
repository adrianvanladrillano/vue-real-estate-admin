<template>
  <div class="columns">
    <div class="column">
      <section class="section">
        <div class="container-fluid">
          <div class="columns">
            <div class="column is-12">
              <h1 class="title is-size-3" style="font-weight: 700">
                Create new listing
              </h1>
            </div>
          </div>

          <div class="columns">
            <div class="column">
              <div class="card px-5 py-5 mb-5">
                <section>
                  <div class="columns mb-5">
                    <div class="column">
                      <h1 class="title is-4">
                        <div
                          style="
                            color: white;
                            background: #00d1b2;
                            border-radius: 50%;
                            height: 30px;
                            width: 30px;
                            display: inline-block;
                            text-align: center;
                          "
                        >
                          1
                        </div>
                        General Information
                      </h1>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column is-8">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium has-text-secondary has-text-weight-medium"
                          >Listing name</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            type="text"
                            v-model="listing_name"
                            placeholder="e.g Alex Smith"
                          />
                        </div>
                      </div>
                    </div>
                    <div class="column">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Property Type</label
                        >
                        <div class="control">
                          <b-autocomplete
                            open-on-focus
                            v-model="listing_type"
                            :data="propertySelect"
                            placeholder="e.g. jQuery"
                            icon="magnify"
                            clearable
                            @select="(option) => (selected = option)"
                          >
                            <template #empty>No results found</template>
                          </b-autocomplete>
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Location</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            v-model="listing_location"
                            type="text"
                            placeholder="e.g. alexsmith@gmail.com"
                          />
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="columns">
                    <div class="column">
                      <div class="field is-6">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Developer</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            type="text"
                            v-model="listing_developer"
                            placeholder="e.g. alexsmith@gmail.com"
                          />
                        </div>
                      </div>
                    </div>

                    <div class="column">
                      <div class="field is-6">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Project</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            v-model="listing_project"
                            type="text"
                            placeholder="e.g. alexsmith@gmail.com"
                          />
                        </div>
                      </div>
                    </div>

                    <div class="column">
                      <div class="field is-6">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Agent</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            v-model="listing_agent"
                            type="text"
                            placeholder="e.g. alexsmith@gmail.com"
                          />
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="columns my-5">
                    <div class="column">
                      <h1 class="title is-4">
                        <div
                          class=""
                          style="
                            color: white;
                            background: #00d1b2;
                            border-radius: 50%;
                            height: 30px;
                            width: 30px;
                            display: inline-block;
                            text-align: center;
                          "
                        >
                          2
                        </div>
                        Pricing Information
                      </h1>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Price</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            v-model="listing_price"
                            icon="magnify"
                            type="text"
                            placeholder="e.g. alexsmith@gmail.com"
                          />
                        </div>
                      </div>
                    </div>

                    <div class="column is-4">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Downpayment</label
                        >
                        <div class="control">
                          <b-autocomplete
                            open-on-focus
                            v-model="listing_down"
                            :data="dpSelect"
                            placeholder="e.g. jQuery"
                            icon="magnify"
                            clearable
                            @select="(option) => (selected = option)"
                          >
                            <template #empty>No results found</template>
                          </b-autocomplete>
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="columns my-5">
                    <div class="column">
                      <h1 class="title is-4">
                        <div
                          class=""
                          style="
                            color: white;
                            background: #00d1b2;
                            border-radius: 50%;
                            height: 30px;
                            width: 30px;
                            display: inline-block;
                            text-align: center;
                          "
                        >
                          3
                        </div>
                        Additional Information
                      </h1>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column is-6">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Bedrooms</label
                        >
                        <b-field>
                          <b-numberinput
                            v-model="listing_bedroom"
                          ></b-numberinput>
                        </b-field>
                      </div>
                    </div>
                    <div class="column is-6">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                          >Bathrooms</label
                        >
                        <div class="control">
                          <b-field>
                            <b-numberinput
                              v-model="listing_bedroom"
                            ></b-numberinput>
                          </b-field>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="columns">
                    <div class="column is-6">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                        >
                          Floor area (m²)</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            type="text"
                            v-model="listing_floor"
                            placeholder="e.g Alex Smith"
                          />
                        </div>
                      </div>
                    </div>

                    <div class="column is-6">
                      <div class="field">
                        <label
                          class="label has-text-secondary has-text-weight-medium"
                        >
                          Land area (m²)</label
                        >
                        <div class="control">
                          <input
                            class="input"
                            v-model="listing_land"
                            type="text"
                            placeholder="e.g Alex Smith"
                          />
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="columns my-5">
                    <div class="column">
                      <h1 class="title is-4">
                        <div
                          class=""
                          style="
                            color: white;
                            background: #00d1b2;
                            border-radius: 50%;
                            height: 30px;
                            width: 30px;
                            display: inline-block;
                            text-align: center;
                          "
                        >
                          3
                        </div>
                        Detailed Information
                      </h1>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column is-12">
                      <b-field label="Message" :label-position="labelPosition">
                        <ckeditor-nuxt v-model="listing_additional" />
                      </b-field>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-field label="Description Image">
                        <b-upload v-model="uploads" multiple drag-drop expanded>
                          <section class="section">
                            <div class="content has-text-centered">
                              <p>
                                <b-icon icon="upload" size="is-large"></b-icon>
                              </p>
                              <p>Drop your files here or click to upload</p>
                            </div>
                          </section>
                        </b-upload>
                      </b-field>
                      <input
                        type="file"
                        multiple
                        accept="image/jpeg"
                        @change="onFileChange"
                      />
                      <div class="columns is-multiline">
                        <div
                          class="column is-4"
                          v-for="(image, key) in images"
                          :key="key"
                        >
                          <div class="card">
                            <div class="card-image">
                              <figure class="image is-4by3">
                                <img class="preview" :ref="'image'" />
                              </figure>
                            </div>
                            <div class="card-content">
                              <p class="">{{ image.name }}</p>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-field label="Amenities">
                        <b-taginput
                          v-model="tags"
                          :data="amenities"
                          autocomplete
                          allow-new="true"
                          open-on-focus="true"
                          field="user.first_name"
                          icon="label"
                          placeholder="Add a tag"
                          @typing="getFilteredTags"
                        >
                        </b-taginput>
                      </b-field>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column is-12">
                      <b-field label="Message" :label-position="labelPosition">
                        <b-input maxlength="200" type="textarea"></b-input>
                      </b-field>
                    </div>
                  </div>
                  <div class="columns">
                    <div class="column">
                      <b-field label="Description Image">
                        <b-upload
                          v-model="dropFiles2"
                          multiple
                          drag-drop
                          expanded
                        >
                          <section class="section">
                            <div class="content has-text-centered">
                              <p>
                                <b-icon icon="upload" size="is-large"></b-icon>
                              </p>
                              <p>Drop your files here or click to upload</p>
                            </div>
                          </section>
                        </b-upload>
                      </b-field>
                    </div>
                  </div>

                  <div class="columns">
                    <div class="column">
                      <b-button type="button" @click="formSubmit()">
                        asd
                      </b-button>
                    </div>
                  </div>
                </section>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import Card from '~/components/Card'
import CkeditorNuxt from '@/components/ckeditor'
import axios from 'axios'
export default {
  name: 'HomePage',

  components: {
    Card,
    CkeditorNuxt,
  },
  data() {
    return {
      listing_name: '',
      listing_location: '',
      listing_type: '',
      listing_agent: '',
      listing_price: '',
      listing_down: '',
      listing_bedroom: '',
      listing_bathroom: '',
      listing_floor: '',
      listing_land: '',
      listing_additional: '',
      listing_landmarks: '',
      listing_developer: '',

      items: [1, 2, 3, 4, 5, 6],
      activeStep: 0,
      dropFiles: [],
      url: null,
      uploads: [],
      images: [],

      propertySelect: [
        'Condominium',
        'House and Lot',
        'Commercial',
        'Apartment',
        'Foreclosures',
        'Lot Only',
      ],
      dpSelect: [
        'No downpayment',
        'Cash basis',
        '10%',
        '20%',
        '30%',
        '40%',
        '50%',
      ],
      amenities: [
        'Gymnasium',
        'Clubhouse',
        'Pet Friendly',
        'Parking',
        'Fully Furnished',
        'Renovated',
        'Smart Home',
      ],
      tags: [],

      showSocial: false,
      isAnimated: true,
      isRounded: true,
      isStepsClickable: false,

      hasNavigation: true,
      customNavigation: false,
      isProfileSuccess: false,

      prevIcon: 'chevron-left',
      nextIcon: 'chevron-right',
      labelPosition: 'bottom',
      mobileMode: 'minimalist',
    }
  },
  methods: {
    formSubmit() {
      axios
        .post('http://localhost:6969/listings', {
          listing_name: this.listing_name,
          listing_location: this.listing_location,
          listing_type: this.listing_type,
          listing_agent: this.listing_agent,
          listing_price: this.listing_price,
          listing_down: this.listing_down,
          listing_bedroom: this.listing_bedroom,
          listing_bathroom: this.listing_bathroom,
          listing_floor: this.listing_floor,
          listing_land: this.listing_land,
          listing_additional: this.listing_additional,
          listing_landmarks: this.listing_landmarks,
          listing_developer: this.listing_developer,
        })
        .then(function (response) {
          console.log(response)
        })
        .catch(function (error) {
          console.log(error)
        })
    },
    onFileChange(e) {
      let vm = this
      var selectedFiles = e.target.files
      for (let i = 0; i < selectedFiles.length; i++) {
        console.log(selectedFiles[i])
        this.images.push(selectedFiles[i])
      }

      for (let i = 0; i < this.images.length; i++) {
        let reader = new FileReader()
        reader.onload = (e) => {
          this.$refs.image[i].src = reader.result

          console.log(this.$refs.image[i].src)
        }

        reader.readAsDataURL(this.images[i])
      }
    },
  },
}
</script>

<style>
#preview img {
  max-width: 100%;
  max-height: 500px;
}
#preview {
  display: flex;
  justify-content: center;
  align-items: center;
}
.ck-editor__editable {
  min-height: 500px;
}
</style>
