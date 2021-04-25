<template>
  <!-- <section class="home">
    <div class="py-24 md:py-36 mx-auto flex flex-wrap flex-col md:flex-row items-center">
      <div class="flex flex-col w-full xl:w-3/5 justify-center lg:items-start overflow-y-hidden">
        <div v-html="$md.render(welcomeText)" class="home__welcome markdown" />

        <div class="mb-12 xl:mb-0">
          <h4 v-if="isSignedUp">Thank you - we'll be in touch shortly.</h4>

          <form
            v-else
            @submit.prevent="handleSubmit"
            name="signups"
            netlify
            class="flex items-center border-b border-b-2 border-blue-400 py-2"
          >
            <input
              ref="emailInput"
              v-model="form.email"
              class="appearance-none mb-36 bg-transparent border-none w-full text-gray-700 mr-3 py-1 px-2 leading-tight focus:outline-none"
              type="text"
              name="email"
              placeholder="your@email.com"
              aria-label="Email address"
            />

            <button
              class="flex-shrink-0 bg-blue-500 hover:bg-blue-700 border-blue-500 hover:border-blue-700 text-sm border-4 text-white py-1 px-2 rounded"
              type="submit"
            >
              Sign Up
            </button>
          </form>
        </div>
      </div>
      <div class="flex flex-col w-full xl:w-2/5">
        <img
          alt="Hero"
          class="rounded shadow-xl"
          src="https://source.unsplash.com/random/720x400"
        />
      </div>
    </div>
  </section> -->
  <main>
    <section class="hero">
      <div class="container">
        <div class="hero-inner">
          <div class="hero-copy">
            <h1 class="hero-title mt-0">{{ welcomeTitle }}</h1>

            <p class="hero-paragraph">
              {{ welcomeDescription }}
            </p>
            <div class="hero-cta">
              <a class="button button-primary" :href="buyLink" target="_blank">Buy it now</a>
              <div class="lights-toggle">
                <input
                  id="lights-toggle"
                  type="checkbox"
                  name="lights-toggle"
                  class="switch"
                  checked="checked"
                />
                <label for="lights-toggle" class="text-xs"
                  ><span>Turn me <span class="label-text">dark</span></span></label
                >
              </div>
            </div>
          </div>
          <div class="hero-media">
            <div class="header-illustration">
              <img
                class="header-illustration-image asset-light"
                src="images/header-illustration-light.svg"
                alt="Header illustration"
              />
              <img
                class="header-illustration-image asset-dark"
                src="images/header-illustration-dark.svg"
                alt="Header illustration"
              />
            </div>
            <div class="hero-media-illustration">
              <img
                class="hero-media-illustration-image asset-light"
                src="images/hero-media-illustration-light.svg"
                alt="Hero media illustration"
              />
              <img
                class="hero-media-illustration-image asset-dark"
                src="images/hero-media-illustration-dark.svg"
                alt="Hero media illustration"
              />
            </div>
            <div class="hero-media-container">
              <!-- <img
                class="hero-media-image asset-light"
                src="images/hero-media-light.svg"
                alt="Hero media"
              />
              <img
                class="hero-media-image asset-dark"
                src="images/hero-media-dark.svg"
                alt="Hero media"
              /> -->
              <CoolLightBox
                :items="items"
                :index="index"
                @close="index = null"
                class="hero-media-container-light-box"
              >
              </CoolLightBox>
              <div class="images-wrappe">
                <div
                  class="hero-media-image-at asset-light play"
                  v-for="(image, imageIndex) in items"
                  :key="imageIndex"
                  @click="index = imageIndex"
                  @keypress="index = imageIndex"
                  :style="{
                    backgroundImage: 'url(' + image.thumb + ')',
                    'background-repeat': 'no-repeat',
                    'background-size': '100% 100%',
                    height: '300px',
                    width: '450px',
                    cursor: 'pointer',
                  }"
                ></div>
                <div
                  class="hero-media-image-at asset-dark play"
                  v-for="(image, imageIndex) in items"
                  :key="imageIndex"
                  @click="index = imageIndex"
                  @keypress="index = imageIndex"
                  :style="{
                    backgroundImage: 'url(' + image.thumb + ')',
                    'background-repeat': 'no-repeat',
                    'background-size': '100% 100%',
                    height: '300px',
                    width: '450px',
                    cursor: 'pointer',
                  }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="features section">
      <div class="container">
        <div class="features-inner section-inner has-bottom-divider">
          <div class="features-header text-center">
            <div class="container-sm">
              <h2 class="section-title mt-0">{{ productTitle }}</h2>
              <p class="section-paragraph">
                {{ productSubTitle }}
              </p>
              <div class="features-image">
                <img
                  class="features-illustration asset-dark"
                  src="images/features-illustration-dark.svg"
                  alt="Feature illustration"
                />
                <img
                  class="features-box asset-dark max-w-xs"
                  :src="productImage"
                  alt="Feature box"
                />
                <img
                  class="features-illustration asset-dark"
                  src="images/features-illustration-top-dark.svg"
                  alt="Feature illustration top"
                />
                <img
                  class="features-illustration asset-light"
                  src="images/features-illustration-light.svg"
                  alt="Feature illustration"
                />
                <img
                  class="features-box asset-light max-w-xs"
                  :src="productImage"
                  alt="Feature box"
                />
                <img
                  class="features-illustration asset-light"
                  src="images/features-illustration-top-light.svg"
                  alt="Feature illustration top"
                />
              </div>
            </div>
          </div>
          <div class="features-wrap">
            <div class="feature is-revealing">
              <div class="feature-inner">
                <div class="feature-icon">
                  <img class="asset-light" src="images/feature-01-light.svg" alt="Feature 01" />
                  <img class="asset-dark" src="images/feature-01-dark.svg" alt="Feature 01" />
                </div>
                <div class="feature-content">
                  <h3 class="feature-title mt-0">MORE INFORMATION</h3>
                  <p class="text-sm mb-0">
                    {{ productDescription }}
                  </p>
                </div>
              </div>
            </div>
            <!-- <div class="feature is-revealing">
              <div class="feature-inner">
                <div class="feature-icon">
                  <img class="asset-light" src="images/feature-02-light.svg" alt="Feature 02" />
                  <img class="asset-dark" src="images/feature-02-dark.svg" alt="Feature 02" />
                </div>
                <div class="feature-content">
                  <h3 class="feature-title mt-0">Discover</h3>
                  <p class="text-sm mb-0">
                    Lorem ipsum dolor sit amet, consecte adipiscing elit, sed do eiusmod tempor
                    incididunt ut labore et dolore magna aliqua dui.
                  </p>
                </div>
              </div>
            </div>
            <div class="feature is-revealing">
              <div class="feature-inner">
                <div class="feature-icon">
                  <img class="asset-light" src="images/feature-03-light.svg" alt="Feature 03" />
                  <img class="asset-dark" src="images/feature-03-dark.svg" alt="Feature 03" />
                </div>
                <div class="feature-content">
                  <h3 class="feature-title mt-0">Discover</h3>
                  <p class="text-sm mb-0">
                    Lorem ipsum dolor sit amet, consecte adipiscing elit, sed do eiusmod tempor
                    incididunt ut labore et dolore magna aliqua dui.
                  </p>
                </div>
              </div>
            </div> -->
          </div>
        </div>
      </div>
    </section>

    <section class="cta section">
      <div class="container-sm">
        <div class="cta-inner section-inner">
          <div class="cta-header text-center">
            <h2 class="section-title mt-0">Get it Now!</h2>
            <p class="section-paragraph">
              {{ welcomeDescription }}
            </p>
            <div class="cta-cta">
              <a class="button button-primary" :href="buyLink" target="_blank">Buy it now</a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';
import CoolLightBox from 'vue-cool-lightbox';
import 'vue-cool-lightbox/dist/vue-cool-lightbox.min.css';

@Component({
  transition() {
    return 'slide-left';
  },
  components: {
    CoolLightBox,
  },
})
export default class Home extends Vue {
  welcomeTitle = settings.welcomeTitle;

  welcomeDescription = settings.welcomeDescription;

  productTitle = settings.productTitle;

  productSubTitle = settings.productSubTitle;

  productImage: any = settings.productImage;

  productDescription = settings.productDescription;

  buyLink = settings.buyLink;

  get posts(): Post[] {
    return this.$store.state.posts;
  }

  isSignedUp = false;

  checked = 'checked';

  items = [
    {
      title: settings.productTitle,
      description: settings.welcomeDescription,
      thumb: settings.productImage,
      src: settings.videoLink,
    },
  ];

  index = null;

  form = {
    email: '',
  };

  mounted(): void {
    const doc = document;
    const { body } = doc;
    const lightSwitch: any = doc.getElementById('lights-toggle');

    window.addEventListener('load', () => {
      body.classList.add('is-loaded');
    });

    function checkLights() {
      const labelText = lightSwitch.parentNode.querySelector('.label-text');
      if (lightSwitch.checked) {
        body.classList.remove('lights-off');
        if (labelText) {
          labelText.innerHTML = 'dark';
        }
      } else {
        body.classList.add('lights-off');
        if (labelText) {
          labelText.innerHTML = 'light';
        }
      }
    }
    // Light switcher
    if (lightSwitch) {
      window.addEventListener('load', checkLights);
      lightSwitch.addEventListener('change', checkLights);
    }
  }

  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  encode(data: any): string {
    return Object.keys(data)
      .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
      .join('&');
  }

  validEmail(email: string): boolean {
    // eslint-disable-next-line
    const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(email);
  }

  async handleSubmit(): Promise<void> {
    if (!this.validEmail(this.form.email)) {
      this.$refs.emailInput.focus();
      return;
    }

    try {
      await fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({ 'form-name': 'signups', ...this.form }),
      });

      this.isSignedUp = true;
    } catch (error) {
      console.error(error);
    }
  }
}
</script>

<style lang="scss" scoped>
.play {
  border-radius: 10% / 10%;
  color: #ffffff;
  font-size: 2em; /* change this to change size */
  margin: 20px auto;
  padding: 0;
  position: relative;
  text-align: center;
  text-indent: 0.1em;
  transition: all 150ms ease-out;
  z-index: 5;
}

.play::after {
  border-style: solid;
  border-width: 1em 0 1em 1.732em;
  border-color: transparent transparent transparent rgba(255, 255, 255, 0.85);
  content: ' ';
  font-size: 0.75em;
  height: 0;
  margin: -1em 0 0 -0.75em;
  top: 50%;
  position: absolute;
  width: 0;
}
</style>
