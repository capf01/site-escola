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
  padding: 100px 0;
  background-color: white;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  margin-top: 50px;
}

.feature-card {
  background-color: var(--light-color);
  border-radius: 10px;
  padding: 30px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.feature-icon {
  font-size: 2.5rem;
  color: var(--primary-color);
  margin-bottom: 20px;
}

.feature-card h3 {
  font-size: 1.5rem;
  margin-bottom: 15px;
  color: var(--dark-color);
}

.feature-card p {
  color: var(--gray-color);
}
</style>