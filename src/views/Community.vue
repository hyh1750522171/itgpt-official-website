<template>
  <div class="community-container">
    <h1>开发者社区</h1>
    
    <div class="community-sections">
      <div class="forum-section">
        <h2>技术讨论</h2>
        <div class="thread" v-for="thread in threads" :key="thread.id">
          <h3>{{ thread.title }}</h3>
          <p>{{ thread.preview }}</p>
          <div class="meta">
            <span class="author">{{ thread.author }}</span>
            <span class="date">{{ thread.date }}</span>
            <span class="comments">{{ thread.comments }} 评论</span>
          </div>
        </div>
      </div>

      <div class="qna-section">
        <h2>问答专区</h2>
        <div class="question" v-for="question in questions" :key="question.id">
          <h3>{{ question.title }}</h3>
          <p>{{ question.preview }}</p>
          <div class="meta">
            <span class="status" :class="question.status">{{ question.status }}</span>
            <span class="answers">{{ question.answers }} 回答</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommunityView',
  data() {
    return {
      threads: [
        {
          id: 1,
          title: 'Vue 3性能优化技巧',
          preview: '分享一些我们在项目中使用的Vue 3性能优化方法...',
          author: '张开发者',
          date: '2023-10-10',
          comments: 12
        },
        {
          id: 2,
          title: '前端微服务架构探讨',
          preview: '讨论前端微服务化的可行方案和实施经验...',
          author: '李架构师',
          date: '2023-10-05', 
          comments: 8
        }
      ],
      questions: [
        {
          id: 1,
          title: '如何解决Vue路由懒加载的问题?',
          preview: '在项目中遇到路由懒加载的一些问题...',
          status: '已解决',
          answers: 3
        },
        {
          id: 2,
          title: '前端权限控制最佳实践',
          preview: '求推荐前端权限控制的实现方案...',
          status: '讨论中',
          answers: 5
        }
      ]
    }
  }
}
</script>

<style scoped>
.community-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
.community-sections {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}
.thread, .question {
  background: #fff;
  padding: 1.5rem;
  margin-bottom: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
.meta {
  display: flex;
  gap: 1rem;
  font-size: 0.9rem;
  color: #7f8c8d;
  margin-top: 0.5rem;
}
.status {
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
}
.status.已解决 {
  background: #e8f5e9;
  color: #2e7d32;
}
.status.讨论中 {
  background: #fff3e0;
  color: #e65100;
}
</style>
