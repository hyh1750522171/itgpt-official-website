<template>
  <main class="home">
    <section class="hero">
      <div class="container">
        <h1 class="animate__animated animate__fadeInDown">
          智能科技 <span>重新定义</span> 未来
        </h1>
        <p class="subtitle animate__animated animate__fadeInDown animate__delay-1s">
          ITGPT提供最前沿的人工智能解决方案，助力企业数字化转型
        </p>
        <div class="cta animate__animated animate__fadeInUp animate__delay-2s">
          <router-link to="/products" class="btn primary">探索产品</router-link>
          <router-link to="/contact" class="btn outline">联系我们</router-link>
        </div>
      </div>
    </section>

    <section class="features">
      <div class="container">
        <h2 class="section-title">我们的优势</h2>
        <div class="features-grid">
          <div 
            v-for="(feature, index) in features" 
            :key="feature.title"
            class="feature-card animate__animated animate__fadeInUp"
            :style="`animation-delay: ${0.3 + index * 0.1}s`"
          >
            <div class="icon">
              <i :class="feature.icon"></i>
            </div>
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      features: [
        {
          icon: 'iconfont icon-ai',
          title: '先进AI技术',
          description: '基于最前沿的深度学习算法'
        },
        {
          icon: 'iconfont icon-cloud',
          title: '云端部署',
          description: '弹性可扩展的云服务架构'
        },
        {
          icon: 'iconfont icon-security',
          title: '企业级安全',
          description: '端到端的数据加密保护'
        },
        {
          icon: 'iconfont icon-customize',
          title: '定制化方案',
          description: '根据业务需求灵活定制'
        }
      ]
    }
  }
}
</script>

<style scoped>
.home {
  padding-top: 2rem;
}

.hero {
  text-align: center;
  padding: 5rem 0;
  background: linear-gradient(135deg, #f9fafb 0%, #e5e7eb 100%);
}

.hero h1 {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: #111827;
}

.hero h1 span {
  color: #4f46e5;
}

.subtitle {
  font-size: 1.2rem;
  color: #6b7280;
  max-width: 600px;
  margin: 0 auto 2rem;
}

.cta {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.btn {
  padding: 0.8rem 1.5rem;
  border-radius: 0.5rem;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.3s ease;
}

.primary {
  background: #4f46e5;
  color: white;
}

.primary:hover {
  background: #4338ca;
}

.outline {
  border: 1px solid #4f46e5;
  color: #4f46e5;
}

.outline:hover {
  background: #4f46e5;
  color: white;
}

.features {
  padding: 5rem 0;
}

.section-title {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 3rem;
  color: #111827;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: white;
  border-radius: 0.5rem;
  padding: 2rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-card .icon {
  font-size: 2rem;
  color: #4f46e5;
  margin-bottom: 1rem;
}

.feature-card h3 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  color: #111827;
}

.feature-card p {
  color: #6b7280;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.2rem;
  }
  
  .cta {
    flex-direction: column;
    align-items: center;
  }
  
  .btn {
    width: 100%;
    max-width: 300px;
  }
}
</style>
