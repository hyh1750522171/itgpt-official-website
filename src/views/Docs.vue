<template>
  <div class="docs-container">
    <div class="docs-sidebar">
      <h2>文档目录</h2>
      <ul>
        <li 
          v-for="section in sections" 
          :key="section.id"
          :class="{active: activeSection === section.id}"
          @click="activeSection = section.id"
        >
          {{ section.title }}
        </li>
      </ul>
    </div>
    
    <div class="docs-content">
      <h1>{{ getActiveSection.title }}</h1>
      <div class="doc-section">
        <p>{{ getActiveSection.content }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DocsView',
  data() {
    return {
      activeSection: 'quickstart',
      sections: [
        {
          id: 'quickstart',
          title: '快速开始',
          content: '项目安装和运行指南...\n1. 安装依赖: pnpm install\n2. 开发模式: pnpm run serve\n3. 构建生产: pnpm run build'
        },
        {
          id: 'api',
          title: 'API 参考', 
          content: '完整的API接口文档...\n- 用户认证API\n- 数据查询API\n- 文件上传API'
        },
        {
          id: 'architecture',
          title: '架构设计',
          content: '系统架构和技术选型...\n前端: Vue 3 + TypeScript\n后端: Node.js + Express\n数据库: MongoDB'
        }
      ]
    }
  },
  computed: {
    getActiveSection() {
      return this.sections.find(s => s.id === this.activeSection) || this.sections[0]
    }
  }
}
</script>

<style scoped>
.docs-container {
  display: flex;
  min-height: calc(100vh - 120px);
}

.docs-sidebar {
  width: 250px;
  padding: 1.5rem;
  background: #f8f9fa;
  border-right: 1px solid #eaeaea;
}

.docs-sidebar h2 {
  margin-top: 0;
  color: #2c3e50;
}

.docs-sidebar ul {
  list-style: none;
  padding: 0;
}

.docs-sidebar li {
  padding: 0.5rem 1rem;
  margin-bottom: 0.5rem;
  cursor: pointer;
  border-radius: 4px;
}

.docs-sidebar li:hover {
  background: #e9ecef;
}

.docs-sidebar li.active {
  background: #e3f2fd;
  color: #1976d2;
}

.docs-content {
  flex: 1;
  padding: 2rem;
  max-width: 800px;
  margin: 0 auto;
}

.doc-section {
  background: #fff;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  white-space: pre-line;
}
</style>
