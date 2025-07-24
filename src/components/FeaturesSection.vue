<template>
  <section id="features" class="features">
    <div class="container">
      <h2 class="section-title">Nossos Diferenciais</h2>
      <p class="section-subtitle">Descubra o que faz da Escola Master Sucesso a melhor escolha para o futuro do seu filho</p>
      
      <div class="features-grid">
        <div class="feature-card" v-for="(feature, index) in features" :key="index">
          <div class="feature-icon">
            <i :class="feature.icon"></i>
          </div>
          <h3>{{ feature.title }}</h3>
          <p>{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FeaturesSection',
  data() {
    return {
      features: [
        {
          icon: 'fas fa-chalkboard-teacher',
          title: 'Professores Qualificados',
          description: 'Nossa equipe é composta por mestres e doutores com vasta experiência em educação.'
        },
        {
          icon: 'fas fa-laptop-code',
          title: 'Tecnologia Educacional',
          description: 'Utilizamos as mais modernas ferramentas tecnológicas para potencializar o aprendizado.'
        },
        {
          icon: 'fas fa-brain',
          title: 'Metodologia Inovadora',
          description: 'Aprendizagem baseada em projetos e desenvolvimento de habilidades do século 21.'
        },
        {
          icon: 'fas fa-medal',
          title: 'Excelência Acadêmica',
          description: 'Destaque nos principais rankings educacionais do país com altas taxas de aprovação.'
        },
        {
          icon: 'fas fa-heart',
          title: 'Acolhimento Personalizado',
          description: 'Acompanhamento individualizado para o desenvolvimento integral de cada aluno.'
        },
        {
          icon: 'fas fa-globe-americas',
          title: 'Visão Global',
          description: 'Programas de intercâmbio e parcerias com instituições internacionais.'
        }
      ]
    }
  }
}
</script>

<style scoped>
.features {
  padding: 80px 0;
  background-color: white;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-title {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 1rem;
  text-align: center;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 4px;
  background-color: var(--primary-color);
  border-radius: 2px;
}

.section-subtitle {
  font-size: 1rem;
  color: var(--gray-color);
  text-align: center;
  max-width: 700px;
  margin: 0 auto 3rem;
  padding: 0 15px;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 25px;
  margin-top: 40px;
}

.feature-card {
  background-color: var(--light-color);
  border-radius: 10px;
  padding: 25px;
  text-align: center;
  transition: all 0.3s ease;
  border: 1px solid rgba(0,0,0,0.05);
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
}

.feature-icon {
  font-size: 2.2rem;
  color: var(--primary-color);
  margin-bottom: 15px;
}

.feature-card h3 {
  font-size: 1.3rem;
  margin-bottom: 12px;
  color: var(--dark-color);
}

.feature-card p {
  color: var(--gray-color);
  line-height: 1.6;
  font-size: 0.95rem;
}

/* Responsividade */
@media (max-width: 992px) {
  .features {
    padding: 70px 0;
  }
  
  .features-grid {
    gap: 20px;
  }
  
  .feature-card {
    padding: 20px;
  }
}

@media (max-width: 768px) {
  .features {
    padding: 60px 0;
  }
  
  .section-title {
    font-size: 1.8rem;
  }
  
  .section-subtitle {
    font-size: 0.95rem;
    margin-bottom: 2.5rem;
  }
  
  .features-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 18px;
  }
  
  .feature-icon {
    font-size: 2rem;
  }
  
  .feature-card h3 {
    font-size: 1.2rem;
  }
}

@media (max-width: 576px) {
  .features {
    padding: 50px 0;
  }
  
  .section-title {
    font-size: 1.6rem;
  }
  
  .section-subtitle {
    margin-bottom: 2rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }
  
  .feature-card {
    padding: 25px 20px;
  }
}

@media (max-width: 400px) {
  .features {
    padding: 40px 0;
  }
  
  .section-title {
    font-size: 1.5rem;
  }
  
  .container {
    padding: 0 15px;
  }
  
  .feature-card h3 {
    font-size: 1.15rem;
  }
  
  .feature-card p {
    font-size: 0.9rem;
  }
}
</style>