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
  padding-top: 0;
}

.hero {
  text-align: center;
  padding: 8rem 0;
  background: linear-gradient(135deg, #0a2540 0%, #0657a3 100%);
}

.hero h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: white;
}

.hero h1 span {
  color: #00d4ff;
}

.subtitle {
  font-size: 1.4rem;
  color: rgba(255, 255, 255, 0.9);
  max-width: 700px;
  margin: 0 auto 3rem;
}

.cta {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 0.5rem;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  font-size: 1.1rem;
}

.primary {
  background: #00d4ff;
  color: #0a2540;
}

.primary:hover {
  background: #00b8e6;
}

.outline {
  border: 2px solid white;
  color: white;
}

.outline:hover {
  background: rgba(255, 255, 255, 0.1);
}

.features {
  padding: 6rem 0;
  background: #f8fafc;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 4rem;
  color: #0a2540;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2.5rem;
}

.feature-card {
  background: white;
  border-radius: 0.75rem;
  padding: 2.5rem;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}

.feature-card .icon {
  font-size: 2.5rem;
  color: #00d4ff;
  margin-bottom: 1.5rem;
}

.feature-card h3 {
  font-size: 1.4rem;
  margin-bottom: 1rem;
  color: #0a2540;
}

.feature-card p {
  color: #64748b;
  line-height: 1.7;
  font-size: 1.1rem;
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
