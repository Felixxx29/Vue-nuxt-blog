<template>
  <article class="post">
    <header class="post-header">
      <div class="post-title">
        <h1>post title</h1>
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
      </div>
      <div class="post-info">
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
        <small>
          <i class="el-icon-view"></i>
          42
        </small>
      </div>
      <div class="post-image">
        <img
          src="https://cdnn21.img.ria.ru/images/155959/50/1559595090_0:261:3160:2039_1920x0_80_0_0_004e7d7ac8637fecc0c1ce27329b923a.jpg"
          alt="post-image"
        >
      </div>
    </header>
    <main class="post-content">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Commodi delectus dolorem dolores exercitationem
        laborum, magnam maxime molestiae natus omnis optio perferendis quia quidem repellat repellendus repudiandae
        sapiente sunt, temporibus unde.
      </p>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Commodi delectus dolorem dolores exercitationem
        laborum, magnam maxime molestiae natus omnis optio perferendis quia quidem repellat repellendus repudiandae
        sapiente sunt, temporibus unde.
      </p>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Commodi delectus dolorem dolores exercitationem
        laborum, magnam maxime molestiae natus omnis optio perferendis quia quidem repellat repellendus repudiandae
        sapiente sunt, temporibus unde.
      </p>
    </main>
    <footer>
      <AppCommentForm
        v-if="canAddComment"
        @created="createCommentHandler"
      />
      <div class="comments" v-if="false">
        <app-comment
          v-for="comment in 4"
          :key="comment"
          :comment="comment"
        />
      </div>
      <div class="text-center" v-else>Комментариев нет</div>
    </footer>
  </article>
</template>

<script>
  import AppComment from "../../components/main/Comment";
  import AppCommentForm from "../../components/main/CommentForm";

  export default {
    validate({params}) {
      return Boolean(params.id)
    },
    data() {
      return {
        canAddComment: true
      }
    },
    name: "id",
    components: {
      AppCommentForm,
      AppComment
    },
    methods: {
      createCommentHandler() {
        this.canAddComment = false
      }
    }
  }
</script>

<style scoped lang="scss">
  .post {
    max-width: 600px;
    margin: 0 auto;
  }

  .post-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  .post-info {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: .5rem;

  }

  .post-image img {
    max-width: 100%;
    height: auto;
  }

  .post-header {
    margin-bottom: 1.5rem;
  }

  .post-content {
    margin-bottom: 2rem;
  }

</style>
