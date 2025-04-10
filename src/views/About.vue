<template>
  <main class="about">
    <section class="hero">
      <div class="container">
        <h1 class="animate__animated animate__fadeInDown">关于ITGPT</h1>
        <p class="subtitle animate__animated animate__fadeInDown animate__delay-1s">
          引领AI技术创新，赋能企业数字化转型
        </p>
      </div>
    </section>

    <section class="about-content">
      <div class="container">
        <div class="about-grid">
          <div class="about-card animate__animated animate__fadeInUp">
            <h2>我们的使命</h2>
            <p>通过前沿的人工智能技术，为企业提供智能化解决方案，推动行业变革与创新。</p>
          </div>
          <div class="about-card animate__animated animate__fadeInUp animate__delay-1s">
            <h2>我们的团队</h2>
            <p>由来自全球顶尖科技公司的AI专家组成，拥有丰富的行业经验和深厚的技术积累。</p>
          </div>
          <div class="about-card animate__animated animate__fadeInUp animate__delay-2s">
            <h2>我们的愿景</h2>
            <p>成为全球领先的企业级AI解决方案提供商，让AI技术真正赋能各行各业。</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'AboutPage'
}
</script>

<style scoped>
.about {
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

.about-content {
  padding: 3rem 0;
}

.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.about-card {
  background: white;
  border-radius: 0.5rem;
  padding: 2rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.about-card h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: #111827;
}

.about-card p {
  color: #6b7280;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
  
  .about-grid {
    grid-template-columns: 1fr;
  }
}
</style>
