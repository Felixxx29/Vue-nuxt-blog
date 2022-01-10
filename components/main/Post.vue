<template>
  <el-card shadow="hover" :body-style="{padding: 0}" class="post">
    <header slot="header" class="post-header">
      <h3>Post title</h3>
      <small>
        <i class="el-icon-time"></i>
        {{ new Date().toLocaleString() }}
      </small>
    </header>
    <div class="post-body">
      <img
        src="https://cdnn21.img.ria.ru/images/155959/50/1559595090_0:261:3160:2039_1920x0_80_0_0_004e7d7ac8637fecc0c1ce27329b923a.jpg"
        class="post-image"
        alt="post-image"
      >
    </div>
    <footer class="post-footer">
      <el-button round @click="openPost">
        открыть пост
      </el-button>
      <span>
        <i class="el-icon-message"></i>
        12
      </span>
    </footer>
  </el-card>
</template>

<script>
  export default {
    name: "Post",
    methods: {
      openPost() {
        const id = 'text-id'
        this.$router.push(`/post/${id}`)
      }
    }
  }
</script>

<style lang="scss" scoped>
  .post {
    margin-bottom: 1.5rem;
  }

  .post-body {
  }

  .post-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .post-image {
    width: 100%;
    display: block;
    height: auto;
  }

  .post-footer {
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
