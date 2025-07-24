<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Entre em Contato</h2>
      <p class="section-subtitle">Agende uma visita ou solicite mais informações sobre nossa escola</p>
      
      <div class="contact-container">
        <div class="contact-info">
          <h3>Informações de Contato</h3>
          <div class="info-item">
            <i class="fas fa-map-marker-alt"></i>
            <p>AV. Oscar Borel, 207 Bairro Compensa II</p>
          </div>
          <div class="info-item">
            <i class="fas fa-map-marker-alt"></i>
            <p>AV. Francisco Queiroz, 54 Bairro Manoa</p>
          </div>
          <div class="info-item">
            <i class="fas fa-map-marker-alt"></i>
            <p>AV. das Oliveiras,120 Bairro Novo Israel</p>
          </div>
          <div class="info-item">
            <i class="fas fa-envelope"></i>
            <p>contato@escolamastersucesso.com.br</p>
          </div>
          <div class="info-item">
            <i class="fas fa-clock"></i>
            <p>Segunda a Sábado: 8h às 18h</p>
          </div>
          <div class="info-item">
            <i class="fas fa-phone-alt"></i>
            <div class="info-content phone-numbers">
              <div class="phone-line">
                <p>(92) 99205-0303</p>
              </div>
              <div class="phone-line">
                <p>(92) 98409-3140</p>
              </div>
              <div class="phone-line">
                <p>(92) 99388-0303</p>
              </div>
            </div>
          </div>
        </div>
        
        <form class="contact-form" @submit.prevent="submitForm">
          <div class="form-group">
            <label for="name">Nome Completo*</label>
            <input type="text" id="name" v-model="form.name" required>
          </div>
          <div class="form-group">
            <label for="email">E-mail*</label>
            <input type="email" id="email" v-model="form.email" required>
          </div>
          <div class="form-group">
            <label for="phone">Telefone/WhatsApp*</label>
            <input type="tel" id="phone" v-model="form.phone" required>
          </div>
          <div class="form-group">
            <label for="student-name">Nome do Aluno (se aplicável)</label>
            <input type="text" id="student-name" v-model="form.studentName">
          </div>
          <div class="form-group">
            <label for="grade">Curso de Interesse</label>
            <select id="grade" v-model="form.grade">
              <option value="">Selecione</option>
              <option value="Atendente de Farmácia">Atendente de Farmácia</option>
              <option value="Operador de Tecnologia Essencial">Operador de Tecnologia Essencial</option>
              <option value="Operador de Tecnologia Avançado">Operador de Tecnologia Avançado</option>
              <option value="Jovem Aprendiz">Jovem Aprendiz</option>
              <option value="Designer Gráfico">Designer Gráfico</option>
              <option value="Gestão Empresarial">Gestão Empresarial</option>
            </select>
          </div>
          <div class="form-group">
            <label for="message">Mensagem*</label>
            <textarea id="message" v-model="form.message" rows="5" required></textarea>
          </div>
          <button type="submit" class="btn btn-primary">
            <i class="fab fa-whatsapp"></i> Enviar via WhatsApp
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactForm',
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        studentName: '',
        grade: '',
        message: ''
      }
    }
  },
  methods: {
    formatPhoneNumber(phone) {
      return phone.replace(/\D/g, '');
    },
    submitForm() {
      const phoneNumber = '559292050303';
      
      let whatsappMessage = `Olá, Escola Master Sucesso! Gostaria de mais informações:\n\n`;
      whatsappMessage += `*Nome:* ${this.form.name}\n`;
      whatsappMessage += `*E-mail:* ${this.form.email}\n`;
      whatsappMessage += `*Telefone:* ${this.form.phone}\n`;
      
      if (this.form.studentName) {
        whatsappMessage += `*Nome do Aluno:* ${this.form.studentName}\n`;
      }
      
      if (this.form.grade) {
        whatsappMessage += `*Série de Interesse:* ${this.form.grade}\n`;
      }
      
      whatsappMessage += `*Mensagem:* ${this.form.message}\n\n`;
      whatsappMessage += `Aguardo retorno, obrigado!`;
      
      const encodedMessage = encodeURIComponent(whatsappMessage);
      const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
      
      if (isMobile) {
        window.open(`https://wa.me/${phoneNumber}?text=${encodedMessage}`);
      } else {
        window.open(`https://web.whatsapp.com/send?phone=${phoneNumber}&text=${encodedMessage}`);
      }
      
      this.resetForm();
    },
    resetForm() {
      this.form = {
        name: '',
        email: '',
        phone: '',
        studentName: '',
        grade: '',
        message: ''
      }
    }
  }
}
</script>

<style scoped>
.contact {
  padding: 60px 0;
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

.contact-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
  margin-top: 30px;
}

.contact-info {
  background-color: var(--light-color);
  padding: 25px;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

.contact-info h3 {
  font-size: 1.3rem;
  margin-bottom: 20px;
  color: var(--dark-color);
}

.info-item {
  display: flex;
  gap: 15px;
  margin-bottom: 15px;
  align-items: flex-start;
}

.info-item i {
  color: var(--primary-color);
  font-size: 1.1rem;
  min-width: 20px;
  margin-top: 3px;
}

.info-item p {
  color: var(--dark-color);
  margin: 0;
  line-height: 1.5;
}

.phone-numbers {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-group label {
  font-weight: 600;
  color: var(--dark-color);
  font-size: 0.95rem;
}

.form-group input,
.form-group textarea,
.form-group select {
  padding: 12px 15px;
  border: 1px solid var(--gray-color);
  border-radius: 6px;
  font-family: inherit;
  font-size: 0.95rem;
  transition: all 0.3s ease;
  width: 100%;
}

.form-group textarea {
  min-height: 120px;
  resize: vertical;
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus {
  outline: none;
  border-color: var(--primary-color);
  box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.2);
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 24px;
  border-radius: 6px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  cursor: pointer;
  border: none;
  font-size: 1rem;
}

.btn-primary {
  background-color: var(--primary-color);
  color: white;
}

.btn-primary:hover {
  background-color: #4338ca;
}

.btn-primary i {
  font-size: 1.2rem;
  margin-right: 8px;
}

/* Responsividade */
@media (max-width: 992px) {
  .contact-container {
    gap: 20px;
  }
  
  .contact-info {
    padding: 20px;
  }
}

@media (max-width: 768px) {
  .contact {
    padding: 50px 0;
  }
  
  .contact-container {
    grid-template-columns: 1fr;
  }
  
  .section-title {
    font-size: 1.8rem;
  }
  
  .section-subtitle {
    font-size: 0.95rem;
    margin-bottom: 2rem;
  }
  
  .contact-info h3 {
    font-size: 1.2rem;
  }
}

@media (max-width: 576px) {
  .contact {
    padding: 40px 0;
  }
  
  .section-title {
    font-size: 1.6rem;
  }
  
  .section-subtitle {
    font-size: 0.9rem;
    margin-bottom: 1.5rem;
  }
  
  .info-item {
    flex-direction: column;
    gap: 5px;
  }
  
  .info-item i {
    margin-top: 0;
  }
  
  .btn {
    padding: 10px 20px;
    font-size: 0.95rem;
    width: 100%;
  }
}

@media (max-width: 400px) {
  .section-title {
    font-size: 1.4rem;
  }
  
  .container {
    padding: 0 15px;
  }
  
  .form-group input,
  .form-group textarea,
  .form-group select {
    padding: 10px 12px;
  }
}
</style>