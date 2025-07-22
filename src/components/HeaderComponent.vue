<template>
  <header class="header">
    <div class="container">
      <nav class="navbar">
        <div class="logo">
          <img src="@/assets/images/logo.jpeg" alt="Escola Master Sucesso">
        </div>
        <ul class="nav-links">
          <li><a href="#home">Início</a></li>
          <li><a href="#features">Diferenciais</a></li>
          <li><a href="#testimonials">Depoimentos</a></li>
          <li><a href="#contact">Contato</a></li>
        </ul>
        <div class="cta">
          <a href="#contact" class="btn btn-primary">Matricule-se</a>
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent'
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
  padding: 20px 0;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo img {
  height: 50px;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 30px;
}

.nav-links a {
  text-decoration: none;
  color: var(--dark-color);
  font-weight: 600;
  transition: color 0.3s ease;
}

.nav-links a:hover {
  color: var(--primary-color);
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
}
</style>