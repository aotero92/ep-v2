<script>
  import Butter from 'buttercms';
const butter = Butter('5e1f0839b8dd099d41053dae2b5e197d2e477111');
  export default {
    name: 'blog-home',
    data() {
      return {
        page_title: '',
        posts: []
      }
    },
    methods: {
      getPosts() {
        butter.post.list({
          page: 1,
          page_size: 10
        }).then(res => {
          this.posts = res.data.data
        })
      }
    },
    created() {
      this.getPosts()
    }
  }
</script>

<template>
  <div id="blog-home">
      <h1>{{ page_title }}</h1>
      <!-- Cree `v-for` y aplique una `key` para Vue. Aquí estamos usando una combinación del `slug` y el índice. -->
      <b-container fluid="sm">
      <div
        v-for="(post,index) in posts"
        :key="post.slug + '_' + index"
      >
        <router-link :to="'/blog/' + post.slug">
          <article class="media">
            <figure>
              <!-- Enlazar resultados usando un `:` -->
              <!-- Use un `v-if`/`else` si es un `featured_image` -->
              <img
                v-if="post.featured_image"
                :src="post.featured_image"
                alt=""
                width= 400, height= auto, class= 'm1'
              >
              <img
                v-else
                src="http://via.placeholder.com/250x250"
                alt=""
              >
            </figure>
            <div>
            <h2>{{ post.title }}</h2>
            
            <p>{{ post.summary }}</p>
            </div>
          </article>
        </router-link>
      </div>
      </b-container>
  </div>
</template>