<template>
  <section id="home" class="hero">
    <div class="container">
      <div class="hero-content">
        <h1>Transformando vidas através da educação</h1>
        <p class="subtitle">Na Escola Master Sucesso, seu futuro começa hoje. Oferecemos educação de qualidade com metodologias inovadoras para formar os líderes de amanhã.</p>
        <div class="hero-buttons">
          <a href="#contact" class="btn btn-primary">Matricule-se agora</a>
          <a href="#features" class="btn btn-secondary">Conheça nossa escola</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection'
}
</script>

<style scoped>
.hero {
  padding: 180px 0 100px;
  background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), 
              url('@/assets/images/hero-bg.png') no-repeat center center/cover;
  color: white;
  text-align: center;
  position: relative;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

.hero h1 {
  font-size: 2.8rem;
  margin-bottom: 20px;
  line-height: 1.2;
  font-weight: 700;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
}

.hero .subtitle {
  font-size: 1.2rem;
  margin-bottom: 30px;
  line-height: 1.6;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.hero-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}

.btn {
  display: inline-block;
  padding: 14px 28px;
  border-radius: 6px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  cursor: pointer;
  border: 2px solid transparent;
  font-size: 1rem;
}

.btn-primary {
  background-color: var(--primary-color);
  color: white;
}

.btn-primary:hover {
  background-color: transparent;
  color: white;
  border-color: white;
}

.btn-secondary {
  background-color: transparent;
  color: white;
  border-color: white;
}

.btn-secondary:hover {
  background-color: white;
  color: var(--dark-color);
}

/* Responsividade */
@media (max-width: 992px) {
  .hero {
    padding: 150px 0 80px;
  }
  
  .hero h1 {
    font-size: 2.5rem;
  }
  
  .hero .subtitle {
    font-size: 1.1rem;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 130px 0 60px;
  }
  
  .hero h1 {
    font-size: 2.2rem;
    margin-bottom: 15px;
  }
  
  .hero .subtitle {
    font-size: 1rem;
    margin-bottom: 25px;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
    gap: 15px;
  }
  
  .btn {
    width: 100%;
    max-width: 280px;
    text-align: center;
  }
}

@media (max-width: 576px) {
  .hero {
    padding: 120px 0 50px;
    background-attachment: scroll;
  }
  
  .hero h1 {
    font-size: 1.8rem;
  }
  
  .hero .subtitle {
    font-size: 0.95rem;
  }
  
  .btn {
    padding: 12px 24px;
    font-size: 0.95rem;
  }
}

@media (max-width: 400px) {
  .hero {
    padding: 100px 0 40px;
  }
  
  .hero h1 {
    font-size: 1.6rem;
  }
  
  .hero .subtitle {
    font-size: 0.9rem;
    margin-bottom: 20px;
  }
  
  .btn {
    padding: 10px 20px;
  }
}
</style>