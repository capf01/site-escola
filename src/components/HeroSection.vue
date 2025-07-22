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
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 20px;
  line-height: 1.2;
}

.hero .subtitle {
  font-size: 1.2rem;
  margin-bottom: 30px;
}

.hero-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
}

@media (max-width: 768px) {
  .hero {
    padding: 150px 0 80px;
  }
  
  .hero h1 {
    font-size: 2.2rem;
  margin-bottom: 15px;
  }
  
  .hero .subtitle {
    font-size: 1rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .hero-buttons .btn {
    width: 100%;
    max-width: 250px;
  }
}
</style>