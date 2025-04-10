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
  background: #0a2540;
  padding: 1.5rem 0;
  position: sticky;
  top: 0;
  z-index: 100;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 3rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 2rem;
  font-weight: 700;
  color: white;
  text-decoration: none;
}

.logo span {
  color: #00d4ff;
}

.nav-links {
  display: flex;
  gap: 3rem;
}

.nav-link {
  color: rgba(255, 255, 255, 0.9);
  text-decoration: none;
  font-weight: 500;
  font-size: 1.1rem;
  transition: color 0.2s ease;
}

.nav-link:hover {
  color: white;
}
</style>
