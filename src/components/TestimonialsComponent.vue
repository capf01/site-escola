<template>
  <section id="testimonials" class="testimonials">
    <div class="container">
      <h2 class="section-title">O que dizem sobre nós</h2>
      <p class="section-subtitle">Depoimentos de pais e alunos que fazem parte da nossa família Master Sucesso</p>
      
      <div class="testimonials-slider">
        <div class="testimonial-card" v-for="(testimonial, index) in testimonials" :key="index">
          <div class="testimonial-content">
            <p class="quote">"{{ testimonial.quote }}"</p>
            <div class="author">
              <img :src="testimonial.avatar" :alt="testimonial.name" class="avatar">
              <div class="author-info">
                <h4>{{ testimonial.name }}</h4>
                <p class="role">{{ testimonial.role }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TestimonialsComponent',
  data() {
    return {
      testimonials: [
        {
          quote: "A Escola Master Sucesso transformou o meu filho. Ele desenvolveu não apenas conhecimento profissional, mas também habilidades sociais e emocionais que o prepararam para a vida.",
          name: "Ana Silva",
          role: "Mãe do aluno Pedro",
          avatar: require('@/assets/images/team1.png')
        },
        {
          quote: "Estudar na Master Sucesso foi a melhor decisão que tomei. Os professores são incríveis e a metodologia me preparou não só para o trabalho, mas para pensar criticamente.",
          name: "Carlos Oliveira",
          role: "Ex-aluno",
          avatar: require('@/assets/images/team2.png')
        },
        {
          quote: "Como educadora, fico impressionada com a qualidade do projeto pedagógico da escola. Meus dois filhos estudam lá e vejo o desenvolvimento deles dia após dia.",
          name: "Mariana Costa",
          role: "Mãe dos alunos Lucas e Julia",
          avatar: require('@/assets/images/team3.png')
        }
      ]
    }
  }
}
</script>

<style scoped>
.testimonials {
  padding: 100px 0;
  background-color: #f8fafc;
}

.testimonials-slider {
  display: flex;
  gap: 30px;
  overflow-x: auto;
  padding: 20px 0;
  scroll-snap-type: x mandatory;
}

.testimonial-card {
  min-width: 350px;
  scroll-snap-align: start;
}

.testimonial-content {
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.quote {
  font-style: italic;
  color: var(--dark-color);
  margin-bottom: 20px;
  font-size: 1.1rem;
}

.author {
  display: flex;
  align-items: center;
  gap: 15px;
}

.avatar {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
}

.author-info h4 {
  color: var(--dark-color);
  margin-bottom: 5px;
}

.role {
  color: var(--gray-color);
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .testimonial-card {
    min-width: 280px;
  }
}
</style>