<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">Welcome to Vuetify</h1>

        <p class="subheading font-weight-regular">
          For help and collaboration with other Vuetify developers,
          <br />please join our online
          <a href="https://community.vuetifyjs.com" target="_blank"
            >Discord Community</a
          >
        </p>
      </v-col>

      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">What's next?</h2>

        <v-row justify="center">
          <a
            v-for="(next, i) in whatsNext"
            :key="i"
            :href="next.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ next.text }}
          </a>
        </v-row>
      </v-col>

      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">Important Links</h2>

        <v-row justify="center">
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ link.text }}
          </a>
        </v-row>

        <v-row justify="center">
          <v-btn @click="increment(1)">Count ({{ counter }})</v-btn>
        </v-row>
      </v-col>

      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">Ecosystem</h2>

        <v-row justify="center">
          <a
            v-for="(eco, i) in ecosystem"
            :key="i"
            :href="eco.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ eco.text }}
          </a>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
import { reactive, ref, defineComponent } from "@vue/composition-api";

export default defineComponent({
  name: "HelloWorld",
  setup() {
    const ecosystem = reactive([
      reactive({
        text: ref("vuetify-loader"),
        href: ref("https://github.com/vuetifyjs/vuetify-loader")
      }),
      reactive({
        text: ref("github"),
        href: ref("https://github.com/vuetifyjs/vuetify")
      }),
      reactive({
        text: ref("awesome-vuetify"),
        href: ref("https://github.com/vuetifyjs/awesome-vuetify")
      })
    ]);

    const importantLinks = reactive([
      reactive({
        text: ref("Documentation"),
        href: ref("https://vuetifyjs.com")
      }),
      reactive({
        text: ref("Chat"),
        href: ref("https://community.vuetifyjs.com")
      }),
      reactive({
        text: ref("Made with Vuetify"),
        href: ref("https://madewithvuejs.com/vuetify")
      }),
      reactive({
        text: ref("Twitter"),
        href: ref("https://twitter.com/vuetifyjs")
      }),
      reactive({
        text: ref("Articles"),
        href: ref("https://medium.com/vuetify")
      })
    ]);

    const whatsNext = reactive([
      reactive({
        text: ref("Explore components"),
        href: ref("https://vuetifyjs.com/components/api-explorer")
      }),
      reactive({
        text: ref("Select a layout"),
        href: ref("https://vuetifyjs.com/getting-started/pre-made-layouts")
      }),
      reactive({
        text: ref("Frequently Asked Questions"),
        href: ref(
          "https://vuetifyjs.com/getting-started/frequently-asked-questions"
        )
      })
    ]);

    const counter = ref(0);

    function increment(value: number) {
      counter.value += value;
    }

    return { ecosystem, importantLinks, whatsNext, counter, increment };
  }
});
</script>
