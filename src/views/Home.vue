<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-4>
        <h1 class="display-2 font-weight-bold mb-3">
          音楽検索画面！！！
        </h1>
        <v-text-field
            v-model="keyword"
            :counter="100"
            label="アーティスト名を入力してください。"
            required
        ></v-text-field>
        <v-btn @click="search">検索</v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    keyword: ''
  }),
  methods: {
    search(){
      this.$router.push(`/result/${this.keyword}`)
    }
  }
};
</script>
