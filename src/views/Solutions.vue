<template>
  <main class="solutions">
    <section class="hero">
      <div class="container">
        <h1 class="animate__animated animate__fadeInDown">解决方案</h1>
        <p class="subtitle animate__animated animate__fadeInDown animate__delay-1s">
          ITGPT为您提供全方位的AI解决方案
        </p>
      </div>
    </section>

    <section class="solution-list">
      <div class="container">
        <div class="solutions-grid">
          <div 
            v-for="(solution, index) in solutions" 
            :key="solution.id"
            class="solution-card animate__animated animate__fadeInUp"
            :style="`animation-delay: ${0.3 + index * 0.1}s`"
          >
            <div class="solution-icon">
              <i :class="solution.icon"></i>
            </div>
            <h3>{{ solution.title }}</h3>
            <p>{{ solution.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'SolutionsPage',
  data() {
    return {
      solutions: [
        {
          id: 'finance',
          icon: 'iconfont icon-finance',
          title: '金融科技',
          description: 'AI驱动的金融风控与智能投顾'
        },
        {
          id: 'healthcare',
          icon: 'iconfont icon-health',
          title: '医疗健康',  
          description: '医疗影像分析与辅助诊断'
        },
        {
          id: 'retail',
          icon: 'iconfont icon-retail',
          title: '零售电商',
          description: '智能推荐与客户行为分析'
        }
      ]
    }
  }
}
</script>

<style scoped>
.solutions {
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

.solution-list {
  padding: 3rem 0;
}

.solutions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.solution-card {
  background: white;
  border-radius: 0.5rem;
  padding: 2rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
  text-align: center;
}

.solution-card:hover {
  transform: translateY(-5px);
}

.solution-icon {
  font-size: 3rem;
  color: #4f46e5;
  margin-bottom: 1rem;
}

.solution-card h3 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: #111827;
}

.solution-card p {
  color: #6b7280;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
  
  .solutions-grid {
    grid-template-columns: 1fr;
  }
}
</style>
