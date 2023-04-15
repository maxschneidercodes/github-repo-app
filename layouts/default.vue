
import { Footer } from '~/.nuxt/components';


import Header from '~/components/Header.vue';

<template>
  <div>
    <Header />
    <div class="p-5">
        <slot />
    </div>
    <Footer />
  </div>
</template>