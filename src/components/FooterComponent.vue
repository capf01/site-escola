<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <img src="@/assets/images/logo.jpeg" alt="Escola Master Sucesso">
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
          <p><i class="fas fa-phone-alt"></i> (92) 9205-0303</p>
          <p><i class="fas fa-envelope"></i> contato@escolamastersucesso.com.br</p>
        </div>
        
        <div class="footer-social">
          <h4>Siga-nos</h4>
          <div class="social-icons">
            <a href="#"><i class="fab fa-facebook-f"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-youtube"></i></a>
            <a href="#"><i class="fab fa-linkedin-in"></i></a>
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
  background-color: var(--dark-color);
  color: white;
  padding: 60px 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-bottom: 40px;
}

.footer-logo img {
  height: 50px;
  margin-bottom: 20px;
}

.footer-logo p {
  color: var(--gray-color);
  margin-top: 15px;
}

.footer-links h4,
.footer-contact h4,
.footer-social h4 {
  font-size: 1.2rem;
  margin-bottom: 20px;
  position: relative;
  padding-bottom: 10px;
}

.footer-links h4::after,
.footer-contact h4::after,
.footer-social h4::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 50px;
  height: 2px;
  background-color: var(--primary-color);
}

.footer-links ul {
  list-style: none;
}

.footer-links li {
  margin-bottom: 10px;
}

.footer-links a {
  color: var(--gray-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: white;
}

.footer-contact p {
  display: flex;
  align-items: center;
  gap: 10px;
  color: var(--gray-color);
  margin-bottom: 15px;
}

.footer-contact i {
  color: var(--primary-color);
}

.social-icons {
  display: flex;
  gap: 15px;
}

.social-icons a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: white;
  transition: all 0.3s ease;
}

.social-icons a:hover {
  background-color: var(--primary-color);
  transform: translateY(-3px);
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 20px;
  text-align: center;
  color: var(--gray-color);
  font-size: 0.9rem;
}
</style>