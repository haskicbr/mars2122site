<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="12">
      <v-card>
        <v-card-title class="headline">
          <h2>road-map</h2>
          {{JSON.stringify(featureItems)}}
        </v-card-title>
        <v-card-text>

        </v-card-text>
        <v-card-actions>
          <v-spacer/>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script type="ts">
const src = "https://trello.com/b/qKB0U7Nm.json";
export default {
  name: "road-map",
  async fetch() {
    const items = await this.$axios.$request({
      url: src,
      headers: {},
      method: "get"
    });

    this.featureItems = items;
  },

  data: () => ({
    featureItems: {}
  })
}
</script>

<style scoped>

</style>
