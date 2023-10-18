<template>
  <v-app-bar
    ><v-app-bar-nav-icon
      ><v-icon icon="mdi-home" @click="$router.push({ name: 'home' })"></v-icon
    ></v-app-bar-nav-icon>
    <div class="lang d-flex align-center" id="lang-toggle" style="gap: 5px">
      <span
        >{{ selected[0].lang }} <v-icon icon="mdi-arrow-down"></v-icon
      ></span>
      <v-menu activator="#lang-toggle">
        <v-list v-model:selected="selected" mandatory>
          <v-list-item v-for="lang in langs" :key="lang.id" :value="lang">
            <v-list-item-title>
              {{ lang.lang }}
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </div>
    {{ langs[0].dir }}
  </v-app-bar>
</template>

<script>
export default {
  data: () => ({
    langs: [
      { id: 2, lang: "Arabic", dir: "rtl" },
      { id: 1, lang: "English", dir: "ltr" },
    ],
    selected: [
      { id: 2, lang: "Arabic", dir: "rtl" },
      { id: 1, lang: "English", dir: "ltr" },
    ],
  }),
};
</script>
