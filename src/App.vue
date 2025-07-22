<template>
  <div class="app">
    <HeaderComponent />
    <main>
      <HeroSection />
      <FeaturesSection />
      <TestimonialsComponent/>
      <ContactForm />
    </main>
    <FooterComponent />
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import ContactForm from './components/ContactForm.vue'
import FooterComponent from './components/FooterComponent.vue'
import TestimonialsComponent from './components/TestimonialsComponent.vue'
export default {
  name: 'App',
  components: {
    HeaderComponent,
    HeroSection,
    FeaturesSection,
    ContactForm,
    TestimonialsComponent,
    FooterComponent
  }
}
</script>

<style>
/* Estilos globais */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');

:root {
  --primary-color: #4f46e5;
  --secondary-color: #10b981;
  --dark-color: #1e293b;
  --light-color: #f8fafc;
  --gray-color: #94a3b8;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Poppins', sans-serif;
  line-height: 1.6;
  color: var(--dark-color);
  background-color: var(--light-color);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.btn {
  display: inline-block;
  padding: 12px 24px;
  border-radius: 6px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  cursor: pointer;
}

.btn-primary {
  background-color: var(--primary-color);
  color: white;
  border: 2px solid var(--primary-color);
}

.btn-primary:hover {
  background-color: transparent;
  color: var(--primary-color);
}

.btn-secondary {
  background-color: var(--secondary-color);
  color: white;
  border: 2px solid var(--secondary-color);
}

.btn-secondary:hover {
  background-color: transparent;
  color: var(--secondary-color);
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
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
  font-size: 1.1rem;
  color: var(--gray-color);
  text-align: center;
  max-width: 700px;
  margin: 0 auto 3rem;
}
</style>