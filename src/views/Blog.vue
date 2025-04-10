<template>
  <div class="blog-container">
    <h1>技术博客</h1>
    <div class="blog-list">
      <!-- 博客列表将在这里动态渲染 -->
      <div class="blog-card" v-for="blog in blogs" :key="blog.id">
        <h2>{{ blog.title }}</h2>
        <p>{{ blog.summary }}</p>
        <span class="date">{{ blog.date }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlogView',
  data() {
    return {
      blogs: [
        {
          id: 1,
          title: 'Vue 3 新特性解析',
          summary: '详细介绍Vue 3的Composition API和其他新特性...',
          date: '2023-10-15'
        },
        {
          id: 2, 
          title: '前端工程化实践',
          summary: '分享我们在项目中实施的前端工程化方案...',
          date: '2023-09-28'
        },
        {
          id: 3,
          title: 'TypeScript实战技巧',
          summary: '分享TypeScript在大型项目中的最佳实践...',
          date: '2023-11-05'
        },
        {
          id: 4,
          title: '前端性能监控方案',
          summary: '构建完整的前端性能监控体系的方法...',
          date: '2023-11-20'
        }
      ]
    }
  }
}
</script>

<style scoped>
.blog-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
}
.blog-card {
  background: #fff;
  padding: 1.5rem;
  margin-bottom: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
.blog-card h2 {
  color: #2c3e50;
  margin-top: 0;
}
.date {
  color: #7f8c8d;
  font-size: 0.9rem;
}
</style>
