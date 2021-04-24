<template>
  <!-- <header class="site-header">
    <div class="container">
      <div class="site-header-inner">
        <div class="brand header-brand">
          <h1 class="m-0">
            <nuxt-link to="/">
              <img class="header-logo-image asset-light" :src="logo" alt="Logo" />
              <img class="header-logo-image asset-dark" :src="logo" alt="Logo" />
            </nuxt-link>
          </h1>
          <nav class="nav ml-auto">
            <ul class="flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">
              <li>
                <nuxt-link to="/blog" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
                  Blog
                </nuxt-link>
              </li>

              <li
                v-for="(page, index) in pages"
                :key="index"
                class="block font-medium px-4 py-1 md:p-2 lg:px-4"
              >
                <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </div>
  </header> -->
  <header class="site-header">
    <div class="container">
      <div class="site-header-inner">
        <div class="brand header-brand">
          <nuxt-link to="/" class="mt-0">
            <img class="header-logo-image asset-light" :src="logo" alt="Logo" />
            <img class="header-logo-image asset-dark" :src="logo" alt="Logo" />
          </nuxt-link>
        </div>
      </div>
    </div>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss"></style>
