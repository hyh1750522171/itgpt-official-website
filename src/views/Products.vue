<template>
  <main class="products">
    <section class="hero">
      <div class="container">
        <h1 class="animate__animated animate__fadeInDown">我们的产品</h1>
        <p class="subtitle animate__animated animate__fadeInDown animate__delay-1s">
          探索ITGPT强大的产品线，助力您的业务增长
        </p>
      </div>
    </section>

    <section class="product-list">
      <div class="container">
        <div class="products-grid">
          <div 
            v-for="(product, index) in products" 
            :key="product.id"
            class="product-card animate__animated animate__fadeInUp"
            :style="`animation-delay: ${0.3 + index * 0.1}s`"
          >
            <div class="product-image">
              <i :class="product.icon"></i>
            </div>
            <h3>{{ product.name }}</h3>
            <p>{{ product.description }}</p>
            <router-link :to="`/products/${product.id}`" class="btn">
              了解更多
            </router-link>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'ProductsPage',
  data() {
    return {
      products: [
        {
          id: 'ai',
          icon: 'iconfont icon-ai',
          name: 'AI解决方案',
          description: '基于深度学习的智能分析平台'
        },
        {
          id: 'cloud',
          icon: 'iconfont icon-cloud',
          name: '云服务',
          description: '弹性可扩展的企业级云架构'
        },
        {
          id: 'enterprise',
          icon: 'iconfont icon-enterprise',
          name: '企业版',
          description: '定制化企业级解决方案'
        }
      ]
    }
  }
}
</script>

<style scoped>
.products {
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

.product-list {
  padding: 3rem 0;
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.product-card {
  background: white;
  border-radius: 0.5rem;
  padding: 2rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
  text-align: center;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-image {
  font-size: 3rem;
  color: #4f46e5;
  margin-bottom: 1rem;
}

.product-card h3 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: #111827;
}

.product-card p {
  color: #6b7280;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.btn {
  display: inline-block;
  padding: 0.6rem 1.2rem;
  background: #4f46e5;
  color: white;
  border-radius: 0.3rem;
  text-decoration: none;
  font-weight: 500;
  transition: background 0.3s ease;
}

.btn:hover {
  background: #4338ca;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
  
  .products-grid {
    grid-template-columns: 1fr;
  }
}
</style>
