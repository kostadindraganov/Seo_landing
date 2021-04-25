<template>
  <footer class="site-footer has-top-divider">
    <div class="container">
      <div class="site-footer-inner">
        <div class="brand footer-brand">
          <a href="#">
            <img class="asset-light w-8" :src="logo" alt="Logo" />
            <img class="asset-dark w-8" :src="logo" alt="Logo" />
          </a>
        </div>
        <!-- <ul class="footer-links list-reset">
          <li>
            <a href="#">Contact</a>
          </li>
          <li>
            <a href="#">About us</a>
          </li>
          <li>
            <a href="#">FAQ's</a>
          </li>
          <li>
            <a href="#">Support</a>
          </li>
        </ul> -->
        <ul class="footer-social-links list-reset">
          <li>
            <a :href="fbLink" target="_blank">
              <span class="screen-reader-text">Facebook</span>
              <svg width="16" height="16" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M6.023 16L6 9H3V6h3V4c0-2.7 1.672-4 4.08-4 1.153 0 2.144.086 2.433.124v2.821h-1.67c-1.31 0-1.563.623-1.563 1.536V6H13l-1 3H9.28v7H6.023z"
                  fill="#FFF"
                />
              </svg>
            </a>
          </li>
          <li>
            <a :href="ytLink" target="_blank">
              <span class="screen-reader-text">Youtube</span>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="#ffffff"
                viewBox="0 0 30 30"
                width="16px"
                height="16px"
              >
                <path
                  d="M 15 4 C 10.814 4 5.3808594 5.0488281 5.3808594 5.0488281 L 5.3671875 5.0644531 C 3.4606632 5.3693645 2 7.0076245 2 9 L 2 15 L 2 15.001953 L 2 21 L 2 21.001953 A 4 4 0 0 0 5.3769531 24.945312 L 5.3808594 24.951172 C 5.3808594 24.951172 10.814 26.001953 15 26.001953 C 19.186 26.001953 24.619141 24.951172 24.619141 24.951172 L 24.621094 24.949219 A 4 4 0 0 0 28 21.001953 L 28 21 L 28 15.001953 L 28 15 L 28 9 A 4 4 0 0 0 24.623047 5.0546875 L 24.619141 5.0488281 C 24.619141 5.0488281 19.186 4 15 4 z M 12 10.398438 L 20 15 L 12 19.601562 L 12 10.398438 z"
                />
              </svg>
            </a>
          </li>
        </ul>
        <div class="footer-copyright">&copy; 2021 Crysal Health Club, all rights reserved</div>
      </div>
    </div>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Footer extends Vue {
  fbLink = settings.fbLink;

  ytLink = settings.ytLink;

  logo = settings.logo;
}
</script>

<style lang="scss"></style>
