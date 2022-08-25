<template>
  <v-container fluid class="pa-2">
    <div v-for="item in resources.items" :key="item.name">
      <a :href="'#' + item.tag">
        {{ item.name }}
      </a>
    </div>
    <div v-for="item in resources.items" :key="item.name">
      <h2 class="mb-2 wrap-list-text anchor" :id="item.tag">
        <b>{{ item.name }}</b>
      </h2>
      <p flat class="my-2">{{ item.desc }}</p>
      <p
        flat
        dense
        class="my-2 "
        v-for="entry in item.values"
        :key="entry.name"
      >
        <span>
          <a v-if="entry.link" :href="entry.link" target="_blank">{{
            entry.name
          }}</a>
          <a
            v-if="entry.download_link"
            :href="entry.download_link"
            target="_blank"
            download
          >
            {{ entry.name }}
          </a>
        </span>
      </p>
      <v-img
        v-if="item.image"
        :src="require(`@/assets/img/tools/${typeof item.image === 'string' ? item.image : item.image.file}`)"
        :alt="typeof item.image === 'string' || !item.image.alt ? undefined : item.image.alt"
      />
    </div>
  </v-container>
</template>

<script>
  import communityData from "@/assets/data/communityData.json";
  import trainingData from "@/assets/data/trainingData.json";
  import resources from "@/assets/data/resources.json";
  export default {
    data: () => ({
      communityData: communityData,
      trainingData: trainingData,
      resources: resources,
    }),
  };
</script>

<style scoped>
  .wrap-list-text {
    -webkit-line-clamp: unset !important;
    white-space: normal;
    overflow-wrap: break-word;
    word-wrap: break-word;
    word-break: normal;
    hyphens: none;
    font-size: 150%;
    color: #1a73e8;
  }
  .anchor {
    padding-top: 1em;
  }
</style>
