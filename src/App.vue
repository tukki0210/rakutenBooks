<template>
  <v-app id="inspire">
    <v-main class="bg-grey-lighten-2 pa-2">
      <div class="ma-2 pa-2">
        <!-- aタグのリンクの代わり -->
          <v-btn>
            <router-link to="/">Home</router-link>
          </v-btn>
          <v-btn>
            <router-link to="/add">Add</router-link>
          </v-btn>
      </div>
      <!-- router/index.jsで書いたコンポーネントが反映 -->
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  // 呼び出す子のコンポーネントを宣言
}

</script>