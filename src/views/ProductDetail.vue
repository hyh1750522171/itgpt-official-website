<template>
  <main class="product-detail">
    <section class="hero">
      <div class="container">
        <h1 class="animate__animated animate__fadeInDown">{{ product.name }}</h1>
        <p class="subtitle animate__animated animate__fadeInDown animate__delay-1s">
          {{ product.tagline }}
        </p>
      </div>
    </section>

    <section class="product-content">
      <div class="container">
        <div class="product-info">
          <div class="product-image">
            <i :class="product.icon"></i>
          </div>
          
          <div class="product-description">
            <h2>产品概述</h2>
            <p>{{ product.description }}</p>
            
            <div class="features">
              <h3>主要功能</h3>
              <ul>
                <li v-for="feature in product.features" :key="feature">
                  {{ feature }}
                </li>
              </ul>
            </div>
            
            <router-link to="/contact" class="btn primary">
              立即咨询
            </router-link>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'ProductDetail',
  data() {
    return {
      products: {
        ai: {
          name: 'AI解决方案',
          icon: 'iconfont icon-ai',
          tagline: '智能驱动业务增长',
          description: '我们的AI解决方案基于最先进的深度学习技术，为企业提供智能分析、预测和决策支持。通过自动化流程和智能洞察，帮助您提升运营效率，发现新的商业机会。',
          features: [
            '自然语言处理(NLP)',
            '计算机视觉(CV)',
            '预测分析',
            '自动化决策',
            '实时数据处理'
          ]
        },
        cloud: {
          name: '云服务',
          icon: 'iconfont icon-cloud',
          tagline: '弹性可扩展的企业级云架构',
          description: 'ITGPT云服务提供安全、可靠的基础设施，支持您的业务快速扩展。我们的云平台具有高可用性、自动扩展和全球部署能力，满足企业级需求。',
          features: [
            '99.99% SLA保证',
            '全球数据中心',
            '自动扩展',
            '企业级安全',
            '混合云支持'
          ]
        },
        enterprise: {
          name: '企业版',
          icon: 'iconfont icon-enterprise',
          tagline: '定制化企业级解决方案',
          description: '针对大型企业的定制化解决方案，结合您的业务需求和技术架构，提供端到端的数字化转型服务，包括咨询、实施和持续优化。',
          features: [
            '专属客户经理',
            '定制开发',
            '优先支持',
            '现场部署',
            '培训服务'
          ]
        }
      }
    }
  },
  computed: {
    product() {
      return this.products[this.$route.params.id] || {}
    }
  }
}
</script>

<style scoped>
.product-detail {
  padding-top: 2rem;
}

.hero {
  text-align: center;
  padding: 3rem 0;
  background: linear-gradient(135deg, #f9fafb 0%, #e5e7eb 100%);
}

.hero h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: #111827;
}

.subtitle {
  font-size: 1.1rem;
  color: #6b7280;
  max-width: 600px;
  margin: 0 auto;
}

.product-content {
  padding: 3rem 0;
}

.product-info {
  display: flex;
  gap: 3rem;
  align-items: flex-start;
}

.product-image {
  flex: 1;
  font-size: 8rem;
  color: #4f46e5;
  text-align: center;
}

.product-description {
  flex: 2;
}

.product-description h2 {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
  color: #111827;
}

.product-description p {
  color: #6b7280;
  line-height: 1.8;
  margin-bottom: 2rem;
}

.features {
  margin: 2rem 0;
}

.features h3 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: #111827;
}

.features ul {
  list-style-type: none;
  padding-left: 0;
}

.features li {
  padding: 0.5rem 0;
  color: #6b7280;
  position: relative;
  padding-left: 1.5rem;
}

.features li::before {
  content: "•";
  color: #4f46e5;
  font-size: 1.5rem;
  position: absolute;
  left: 0;
  top: 0.2rem;
}

.btn {
  display: inline-block;
  padding: 0.8rem 1.5rem;
  background: #4f46e5;
  color: white;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 500;
  transition: background 0.3s ease;
}

.btn:hover {
  background: #4338ca;
}

@media (max-width: 768px) {
  .product-info {
    flex-direction: column;
  }
  
  .product-image {
    font-size: 5rem;
    margin-bottom: 2rem;
  }
}
</style>
