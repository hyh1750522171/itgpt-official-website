<template>
  <footer class="footer animate__animated animate__fadeInUp">
    <div class="container">
      <div class="footer-content">
        <div class="brand-info">
          <h3 class="logo">IT<span>GPT</span></h3>
          <p class="slogan">智能科技 引领未来</p>
        </div>

        <div class="footer-links">
          <div class="link-group" v-for="group in linkGroups" :key="group.title">
            <h4>{{ group.title }}</h4>
            <router-link 
              v-for="link in group.links" 
              :key="link.path"
              :to="link.path"
              class="footer-link"
            >
              {{ link.text }}
            </router-link>
          </div>
        </div>

        <div class="social-links">
          <h4>关注我们</h4>
          <div class="social-icons">
            <a v-for="social in socials" :key="social.name" :href="social.url" target="_blank">
              <i :class="social.icon"></i>
            </a>
          </div>
        </div>
      </div>

      <div class="copyright">
        <p>&copy; {{ currentYear }} ITGPT 版权所有</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'AppFooter',
  data() {
    return {
      currentYear: new Date().getFullYear(),
      linkGroups: [
        {
          title: '产品',
          links: [
            { path: '/products/ai', text: 'AI解决方案' },
            { path: '/products/cloud', text: '云服务' },
            { path: '/products/enterprise', text: '企业版' }
          ]
        },
        {
          title: '资源',
          links: [
            { path: '/blog', text: '技术博客' },
            { path: '/docs', text: '开发文档' },
            { path: '/community', text: '开发者社区' }
          ]
        }
      ],
      socials: [
        { name: 'weibo', url: '#', icon: 'iconfont icon-weibo' },
        { name: 'wechat', url: '#', icon: 'iconfont icon-wechat' },
        { name: 'github', url: '#', icon: 'iconfont icon-github' },
        { name: 'linkedin', url: '#', icon: 'iconfont icon-linkedin' }
      ]
    }
  }
}
</script>

<style scoped>
.footer {
  background: #f9fafb;
  padding: 3rem 0 1rem;
  margin-top: auto;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.footer-content {
  display: flex;
  flex-wrap: wrap;
  gap: 3rem;
  margin-bottom: 2rem;
}

.brand-info {
  flex: 1;
  min-width: 200px;
}

.logo {
  font-size: 1.8rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 1rem;
}

.logo span {
  color: #4f46e5;
}

.slogan {
  color: #6b7280;
  font-size: 0.9rem;
}

.footer-links {
  flex: 2;
  display: flex;
  gap: 3rem;
  flex-wrap: wrap;
}

.link-group {
  min-width: 120px;
}

.link-group h4 {
  font-size: 1rem;
  color: #111827;
  margin-bottom: 1rem;
}

.footer-link {
  display: block;
  color: #6b7280;
  text-decoration: none;
  margin-bottom: 0.5rem;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: #4f46e5;
}

.social-links {
  flex: 1;
  min-width: 200px;
}

.social-links h4 {
  font-size: 1rem;
  color: #111827;
  margin-bottom: 1rem;
}

.social-icons {
  display: flex;
  gap: 1rem;
}

.social-icons a {
  color: #6b7280;
  font-size: 1.2rem;
  transition: color 0.3s ease;
}

.social-icons a:hover {
  color: #4f46e5;
}

.copyright {
  border-top: 1px solid #e5e7eb;
  padding-top: 1.5rem;
  text-align: center;
  color: #6b7280;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .footer-content {
    flex-direction: column;
  }
  
  .footer-links {
    flex-direction: column;
    gap: 2rem;
  }
}
</style>
