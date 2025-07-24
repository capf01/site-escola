<template>
  <header class="header">
    <div class="container">
      <nav class="navbar">
        <div class="logo">
          <img src="@/assets/images/logo (2).jpeg" alt="Escola Master Sucesso">
        </div>
        
        <!-- Menu para desktop -->
        <ul class="nav-links desktop-menu">
          <li><a href="#home">Início</a></li>
          <li><a href="#features">Diferenciais</a></li>
          <li><a href="#testimonials">Depoimentos</a></li>
          <li><a href="#contact">Contato</a></li>
        </ul>
        
        <!-- Botão CTA para desktop -->
        <div class="cta desktop-cta">
          <a href="#contact" class="btn btn-primary">Matricule-se</a>
        </div>
        
        <!-- Ícone do menu mobile -->
        <button class="mobile-menu-toggle" @click="toggleMobileMenu">
          <i class="fas fa-bars"></i>
        </button>
      </nav>
      
      <!-- Menu mobile -->
      <div class="mobile-menu" :class="{ 'active': isMobileMenuOpen }">
        <ul class="mobile-nav-links">
          <li><a href="#home" @click="closeMobileMenu">Início</a></li>
          <li><a href="#features" @click="closeMobileMenu">Diferenciais</a></li>
          <li><a href="#testimonials" @click="closeMobileMenu">Depoimentos</a></li>
          <li><a href="#contact" @click="closeMobileMenu">Contato</a></li>
        </ul>
        <div class="mobile-cta">
          <a href="#contact" class="btn btn-primary" @click="closeMobileMenu">Matricule-se</a>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      isMobileMenuOpen: false
    }
  },
  methods: {
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen
    },
    closeMobileMenu() {
      this.isMobileMenuOpen = false
    }
  }
}
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background-color: white;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  padding: 10px 0;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
}

.logo img {
  height: 80px;
  width: 80px;
  border-radius: 50%;
  object-fit: cover;
  object-position: center;
  transition: transform 0.3s ease;
}

.logo img:hover {
  transform: scale(1.05);
}

/* Estilos do menu desktop */
.desktop-menu {
  display: flex;
  list-style: none;
  gap: 30px;
  margin: 0;
  padding: 0;
}

.desktop-menu a {
  text-decoration: none;
  color: var(--dark-color);
  font-weight: 600;
  font-size: 1rem;
  transition: color 0.3s ease;
  position: relative;
  padding: 5px 0;
}

.desktop-menu a:hover {
  color: rgba(2, 6, 250, 0.933);
}

.desktop-menu a::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--primary-color);
  transition: width 0.3s ease;
}

.desktop-menu a:hover::after {
  width: 100%;
}

.desktop-cta .btn {
  padding: 10px 20px;
  font-size: 0.9rem;
}

/* Estilos do menu mobile */
.mobile-menu-toggle {
  display: none;
  background: none;
  border: none;
  color: var(--dark-color);
  font-size: 1.5rem;
  cursor: pointer;
  padding: 10px;
}

.mobile-menu {
  display: none;
  position: fixed;
  top: 100px;
  left: 0;
  right: 0;
  background-color: white;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  padding: 20px;
  transform: translateY(-150%);
  transition: transform 0.3s ease;
  z-index: 999;
}

.mobile-menu.active {
  transform: translateY(0);
}

.mobile-nav-links {
  list-style: none;
  padding: 0;
  margin: 0 0 20px 0;
}

.mobile-nav-links li {
  margin-bottom: 15px;
}

.mobile-nav-links a {
  text-decoration: none;
  color: var(--dark-color);
  font-weight: 600;
  font-size: 1.1rem;
  display: block;
  padding: 8px 0;
  transition: color 0.3s ease;
}

.mobile-nav-links a:hover {
  color: var(--primary-color);
}

.mobile-cta .btn {
  width: 100%;
  text-align: center;
  padding: 12px;
  font-size: 1rem;
}

/* Responsividade */
@media (max-width: 992px) {
  .desktop-menu {
    gap: 20px;
  }
  
  .logo img {
    height: 70px;
    width: 70px;
  }
}

@media (max-width: 768px) {
  .desktop-menu,
  .desktop-cta {
    display: none;
  }
  
  .mobile-menu-toggle {
    display: block;
  }
  
  .mobile-menu {
    display: block;
  }
  
  .logo img {
    height: 60px;
    width: 60px;
  }
}

@media (max-width: 576px) {
  .header {
    padding: 8px 0;
  }
  
  .mobile-menu {
    top: 76px;
  }
  
  .logo img {
    height: 50px;
    width: 50px;
  }
}
</style>