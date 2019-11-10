<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-1>
        <h1 class="display-2 font-weight-bold mb-2">
          検索結果！
        </h1>
        <p class="subheading font-weight-regular">
          検索キーワード：{{ this.$route.params.keyword }}
        </p>
      </v-flex>

      <v-flex
        mb-5
        xs12
      >

            <div style="margin-bottom:10px" v-for="(item, i) in albums" :key="i">
              <v-card
                color="grey darken-4"
                dark
                :href="item.collectionViewUrl"
                target="_blank"
              >
                <v-list-item three-line>
                  <v-list-item-avatar
                    size="125"
                    tile
                  >
                    <v-img :src="item.artworkUrl100"></v-img>
                  </v-list-item-avatar>
                  <v-list-item-content class="align-self-start">
                    <v-list-item-title
                      class="headline mb-2"
                      v-text="item.collectionName"
                    ></v-list-item-title>
                    <v-list-item-subtitle v-text="item.artistName"></v-list-item-subtitle>
                  </v-list-item-content>
                </v-list-item>
              </v-card>
            </div>

      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    albums: [],
  }),
  created(){
    this.$axios.get(`iTunesApiUrlGoesHere!`) // see https://www.youtube.com/watch?v=8Dv23fu8G_g
      .then((response) => {
        console.log(response.data.results)
        this.albums = response.data.results
      });
  }
};
</script>
