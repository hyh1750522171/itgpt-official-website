<template>
  <main class="contact">
    <section class="hero">
      <div class="container">
        <h1 class="animate__animated animate__fadeInDown">联系我们</h1>
        <p class="subtitle animate__animated animate__fadeInDown animate__delay-1s">
          随时为您提供专业咨询与服务
        </p>
      </div>
    </section>

    <section class="contact-content">
      <div class="container">
        <div class="contact-grid">
          <div class="contact-form animate__animated animate__fadeInLeft">
            <h2>发送消息</h2>
            <form @submit.prevent="submitForm">
              <div class="form-group">
                <label for="name">姓名</label>
                <input type="text" id="name" v-model="form.name" required>
              </div>
              <div class="form-group">
                <label for="email">邮箱</label>
                <input type="email" id="email" v-model="form.email" required>
              </div>
              <div class="form-group">
                <label for="message">留言</label>
                <textarea id="message" v-model="form.message" required></textarea>
              </div>
              <button type="submit" class="btn">提交</button>
            </form>
          </div>

          <div class="contact-info animate__animated animate__fadeInRight">
            <h2>联系方式</h2>
            <div class="info-item">
              <i class="iconfont icon-location"></i>
              <p>上海市浦东新区张江高科技园区</p>
            </div>
            <div class="info-item">
              <i class="iconfont icon-phone"></i>
              <p>400-888-8888</p>
            </div>
            <div class="info-item">
              <i class="iconfont icon-email"></i>
              <p>contact@itgpt.com</p>
            </div>
            <div class="info-item">
              <i class="iconfont icon-time"></i>
              <p>周一至周五 9:00-18:00</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'ContactPage',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      // 这里可以添加表单提交逻辑
      alert('感谢您的留言，我们会尽快回复您！');
      this.form = {
        name: '',
        email: '',
        message: ''
      };
    }
  }
}
</script>

<style scoped>
.contact {
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

.contact-content {
  padding: 3rem 0;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
}

.contact-form, .contact-info {
  background: white;
  border-radius: 0.5rem;
  padding: 2rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.contact-form h2, .contact-info h2 {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  color: #111827;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
  color: #374151;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #d1d5db;
  border-radius: 0.375rem;
  font-size: 1rem;
}

.form-group textarea {
  min-height: 120px;
}

.btn {
  background: #4f46e5;
  color: white;
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 0.375rem;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.3s ease;
}

.btn:hover {
  background: #4338ca;
}

.info-item {
  display: flex;
  align-items: center;
  margin-bottom: 1.5rem;
}

.info-item i {
  font-size: 1.5rem;
  color: #4f46e5;
  margin-right: 1rem;
}

.info-item p {
  color: #6b7280;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>
