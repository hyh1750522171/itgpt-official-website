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
  background: #0a2540;
  padding: 4rem 0 2rem;
  margin-top: auto;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 3rem;
}

.footer-content {
  display: flex;
  flex-wrap: wrap;
  gap: 4rem;
  margin-bottom: 3rem;
}

.brand-info {
  flex: 1;
  min-width: 250px;
}

.logo {
  font-size: 2rem;
  font-weight: 700;
  color: white;
  margin-bottom: 1.5rem;
}

.logo span {
  color: #00d4ff;
}

.slogan {
  color: rgba(255, 255, 255, 0.8);
  font-size: 1rem;
}

.footer-links {
  flex: 2;
  display: flex;
  gap: 4rem;
  flex-wrap: wrap;
}

.link-group {
  min-width: 150px;
}

.link-group h4 {
  font-size: 1.2rem;
  color: white;
  margin-bottom: 1.5rem;
}

.footer-link {
  display: block;
  color: rgba(255, 255, 255, 0.7);
  text-decoration: none;
  margin-bottom: 0.8rem;
  transition: color 0.3s ease;
  font-size: 1rem;
}

.footer-link:hover {
  color: #00d4ff;
}

.social-links {
  flex: 1;
  min-width: 250px;
}

.social-links h4 {
  font-size: 1.2rem;
  color: white;
  margin-bottom: 1.5rem;
}

.social-icons {
  display: flex;
  gap: 1.5rem;
}

.social-icons a {
  color: rgba(255, 255, 255, 0.7);
  font-size: 1.5rem;
  transition: color 0.3s ease;
}

.social-icons a:hover {
  color: #00d4ff;
}

.copyright {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 2rem;
  text-align: center;
  color: rgba(255, 255, 255, 0.6);
  font-size: 1rem;
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
