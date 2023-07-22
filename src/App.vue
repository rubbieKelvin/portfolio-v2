<template>
  <div class="h-full container">
    <div class="bummer" />
    <div class="h-full flex flex-col-reverse lg:flex-row z-10 relative">
      <div
        socials
        class="lg:min-w-[20%] py-12 px-8 lg:p-0 flex justify-around lg:justify-center lg:flex-col items-center gap-9"
      >
        <a
          v-for="link in links"
          :href="link.link"
          :key="link.link"
          :title="link.name"
          class="opacity-40 hover:opacity-100 text-white lg:text-black"
        >
          <component :is="link.icon" :size="34" />
        </a>
      </div>
      <div main class="flex items-center h-full px-16 lg:p-0">
        <div class="flex gap-8 lg:gap-4 flex-col">
          <h1 class="heading text-7xl">Hey there, i'm<br />rubbie kelvin.</h1>
          <p class="text-2xl">I build things that works</p>
          <a class="text-base bg-black rounded-md text-white px-5 py-4 w-max">
            Download resume
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import {
  IconBrandGithub,
  IconBrandGoogle,
  IconBrandLinkedin,
  IconBrandTwitter,
} from "@tabler/icons-vue";

export default defineComponent({
  components: { IconBrandTwitter },
  setup() {
    const links = [
      {
        name: "twitter",
        link: "https://twitter.com/KelvinRubbie",
        icon: IconBrandTwitter,
      },
      {
        name: "github",
        link: "https://github.com/rubbiekelvin",
        icon: IconBrandGithub,
      },
      {
        name: "Email",
        link: "mailto:dev.rubbie@gmail.com",
        icon: IconBrandGoogle,
      },
      {
        name: "linkedin",
        link: "https://www.linkedin.com/in/rubbiekelvinvoltsman/",
        icon: IconBrandLinkedin,
      },
    ];

    return { links };
  },
});
</script>

<style lang="scss" scoped>
.bummer {
  $size: calc(100vh - 5em);
  position: fixed;
  background: var(--theme, #000);
  width: 160vw;
  height: 100vh;
  bottom: -80%;
  border-radius: 80vw;
  z-index: 1;
  right: -28%;

  @screen lg {
    height: $size;
    border-radius: calc($size / 2);
    width: $size;
    right: calc(40em - $size);
    bottom: -15%;
  }
}

h1.heading {
  line-height: normal;
}
</style>
