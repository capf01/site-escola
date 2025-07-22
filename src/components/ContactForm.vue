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
            <p>Rua da Educação, 123 - Bairro do Saber, Cidade - SP</p>
          </div>
          <div class="info-item">
            <i class="fas fa-phone-alt"></i>
            <p>(11) 1234-5678</p>
          </div>
          <div class="info-item">
            <i class="fas fa-envelope"></i>
            <p>contato@escolamastersucesso.com.br</p>
          </div>
          <div class="info-item">
            <i class="fas fa-clock"></i>
            <p>Segunda a Sexta: 7h às 19h</p>
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
            <label for="grade">Série de Interesse</label>
            <select id="grade" v-model="form.grade">
              <option value="">Selecione</option>
              <option value="Atendente de Farmácia">Atendente de Farmácia</option>
              <option value="Operador de Tecnologia Essencial">Operador de Tecnologia Essencial</option>
              <option value="Operador de Tecnologia Avançado">Operador de Tecnologia Avançado</option>
              <option value="Jovem Aprendiz">Jovem Aprendiz</option>
              1<option value="Designer Gráfico">Designer Gráfico</option>
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
      // Remove tudo que não é dígito
      return phone.replace(/\D/g, '');
    },
    submitForm() {
      const phoneNumber = '5592984713059';
      
      // Monta a mensagem para o WhatsApp
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
      
      // Codifica a mensagem para URL
      const encodedMessage = encodeURIComponent(whatsappMessage);
      
      // Verifica se é mobile para abrir o WhatsApp apropriadamente
      const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
      
      if (isMobile) {
        // Abre no app do WhatsApp
        window.open(`https://wa.me/${phoneNumber}?text=${encodedMessage}`);
      } else {
        // Abre no WhatsApp Web para desktop
        window.open(`https://web.whatsapp.com/send?phone=${phoneNumber}&text=${encodedMessage}`);
      }
      
      // Reseta o formulário
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
  padding: 100px 0;
  background-color: white;
}

.contact-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 50px;
  margin-top: 50px;
}

.contact-info {
  background-color: var(--light-color);
  padding: 30px;
  border-radius: 10px;
}

.contact-info h3 {
  font-size: 1.5rem;
  margin-bottom: 20px;
  color: var(--dark-color);
}

.info-item {
  display: flex;
  gap: 15px;
  margin-bottom: 20px;
}

.info-item i {
  color: var(--primary-color);
  font-size: 1.2rem;
  margin-top: 3px;
}

.info-item p {
  color: var(--dark-color);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-group label {
  font-weight: 600;
  color: var(--dark-color);
}

.form-group input,
.form-group textarea,
.form-group select {
  padding: 12px 15px;
  border: 1px solid var(--gray-color);
  border-radius: 6px;
  font-family: inherit;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus {
  outline: none;
  border-color: var(--primary-color);
}

button[type="submit"] {
  align-self: flex-start;
  display: flex;
  align-items: center;
  gap: 10px;
}

.btn-primary i {
  font-size: 1.2rem;
}
</style>