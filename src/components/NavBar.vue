<template>
  <header class="navbar">
    <div class="container">
      <router-link to="/" class="logo animate__animated animate__fadeIn">
        <span>IT</span>GPT
      </router-link>
      
      <nav class="nav-links">
        <router-link 
          v-for="link in links" 
          :key="link.path"
          :to="link.path"
          class="nav-link animate__animated animate__fadeIn"
        >
          {{ link.text }}
        </router-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      links: [
        { path: '/', text: '首页' },
        { path: '/products', text: '产品' },
        { path: '/solutions', text: '解决方案' },
        { path: '/about', text: '关于我们' },
        { path: '/contact', text: '联系我们' }
      ]
    }
  }
}
</script>

<style scoped>
.navbar {
  background: white;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 100;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.8rem;
  font-weight: 700;
  color: #333;
  text-decoration: none;
}

.logo span {
  color: #4f46e5;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: #4b5563;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: #4f46e5;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: #4f46e5;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}
</style>
