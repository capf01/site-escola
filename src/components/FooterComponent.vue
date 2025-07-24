<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <img src="@/assets/images/logo (2).jpeg" alt="Escola Master Sucesso">
          <p>Transformando vidas através da educação de excelência.</p>
        </div>
        
        <div class="footer-links">
          <h4>Links Rápidos</h4>
          <ul>
            <li><a href="#home">Início</a></li>
            <li><a href="#features">Diferenciais</a></li>
            <li><a href="#testimonials">Depoimentos</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </div>
        
        <div class="footer-contact">
          <h4>Contato</h4>
          <p><i class="fas fa-map-marker-alt"></i> AV. Oscar Borel, 207 Bairro Compensa II</p>
          <p><i class="fas fa-map-marker-alt"></i> AV. Francisco Queiroz, 54 Bairro Manoa</p>
          <p><i class="fas fa-map-marker-alt"></i> AV. das Oliveiras,120 Bairro Novo Israel</p>
          <p><i class="fas fa-phone-alt"></i> (92) 99205-0303</p>
          <p><i class="fas fa-phone-alt"></i> (92) 98409-3140</p>
          <p><i class="fas fa-phone-alt"></i> (92) 99388-0303</p>
          <p><i class="fas fa-envelope"></i> contato@escolamastersucesso.com.br</p>
        </div>
        
        <div class="footer-social">
          <h4>Siga-nos</h4>
          <div class="social-icons">
            <a href="https://www.instagram.com/escolasmaissucesso?igsh=azduOHNhOHY3bnhv" 
               target="_blank" 
               rel="noopener noreferrer" 
               class="social-icon-circle">
              <img src="@/assets/images/instagram.png" alt="Instagram">
            </a>
            <a href="https://www.facebook.com/suapagina" target="_blank" rel="noopener noreferrer" class="social-icon-circle">
              <img src="@/assets/images/facebook.jpeg" alt="Facebook">
            </a>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; 2024 Escola Master Sucesso. Todos os direitos reservados.</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponent'
}
</script>

<style scoped>
.footer {
  background-color: #011335;
  color: white;
  padding: 50px 0 20px;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
  margin-bottom: 30px;
}

.footer-logo img {
  width: 100px;
  height: 100px;
  border-radius: 100%;
  margin-bottom: 15px;
}

.footer-logo p {
  color: var(--gray-color);
  margin-top: 10px;
  line-height: 1.6;
}

.footer-links h4,
.footer-contact h4,
.footer-social h4 {
  font-size: 1.2rem;
  margin-bottom: 15px;
  position: relative;
  padding-bottom: 8px;
}

.footer-links h4::after,
.footer-contact h4::after,
.footer-social h4::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 40px;
  height: 2px;
  background-color: var(--primary-color);
}

.footer-links ul {
  list-style: none;
  padding: 0;
}

.footer-links li {
  margin-bottom: 8px;
}

.footer-links a {
  color: var(--gray-color);
  text-decoration: none;
  transition: color 0.3s ease;
  font-size: 0.95rem;
}

.footer-links a:hover {
  color: white;
}

.footer-contact p {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  color: var(--gray-color);
  margin-bottom: 12px;
  font-size: 0.9rem;
  line-height: 1.5;
}

.footer-contact i {
  color: var(--primary-color);
  margin-top: 3px;
  min-width: 16px;
}

.social-icons {
  display: flex;
  gap: 12px;
  align-items: center;
}

.social-icon-circle {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 38px;
  height: 38px;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  transition: all 0.3s ease;
  overflow: hidden;
}

.social-icon-circle:hover {
  background-color: var(--primary-color);
  transform: translateY(-3px);
}

.social-icon-circle img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 20px;
  text-align: center;
  color: var(--gray-color);
  font-size: 0.85rem;
}

/* Responsividade */
@media (max-width: 992px) {
  .footer {
    padding: 40px 0 20px;
  }
  
  .footer-content {
    gap: 25px;
  }
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
  
  .footer-logo {
    grid-column: 1 / -1;
    text-align: center;
  }
  
  .footer-logo img {
    margin-left: auto;
    margin-right: auto;
  }
  
  .footer-links h4::after,
  .footer-contact h4::after,
  .footer-social h4::after {
    left: 50%;
    transform: translateX(-50%);
  }
}

@media (max-width: 576px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 25px;
  }
  
  .footer-links ul,
  .footer-contact p {
    justify-content: center;
  }
  
  .footer-contact p {
    justify-content: center;
    text-align: center;
  }
  
  .social-icons {
    justify-content: center;
  }
  
  .footer-links h4::after,
  .footer-contact h4::after,
  .footer-social h4::after {
    left: 50%;
    transform: translateX(-50%);
  }
}

@media (max-width: 400px) {
  .footer {
    padding: 30px 0 15px;
  }
  
  .footer-contact p {
    font-size: 0.85rem;
  }
  
  .footer-bottom p {
    font-size: 0.8rem;
  }
}
</style>