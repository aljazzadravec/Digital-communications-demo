<template>
  <div class="flex flex-row items-center justify-end gap-4">
    <!-- Scheme switcher -->
    <scheme-switcher v-if="isLgUp" />
    <!-- GitHub link -->
    <app-github-icon v-if="isLgUp" />
  </div>
</template>

<script
  setup
  lang="ts"
>
import SchemeSwitcher from "@/js/components/common/navigation/SchemeSwitcher.vue";
import {useStore} from "vuex";
import {State} from "@/js/store/store";
import {computed} from "vue";
import AppGithubIcon from "@/js/components/common/icons/AppGithubIcon.vue";


const store = useStore<State>();
const isLgUp = computed<boolean>(() => store.getters['deviceProperties/isLgUp']);
</script>