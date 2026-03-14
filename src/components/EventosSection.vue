<script setup>
const eventos = [
  { icon: '☕', title: 'Café com Gurias',          desc: 'Primeiro encontro presencial da comunidade. Risadas, trocas e muita conexão!', date: 'JAN 2025' },
  { icon: '🎤', title: 'Roda de Conversa',         desc: 'Papo aberto sobre autoconhecimento, propósito e o que nos move no dia a dia.', date: 'FEV 2025' },
  { icon: '🌸', title: 'Workshop de Bem-estar',    desc: 'Práticas de autocuidado e bem-estar para equilibrar vida pessoal e profissional.', date: 'MAR 2025' },
  { icon: '🎉', title: 'Aniversário da Comunidade', desc: 'Celebração de 1 ano com presença especial e muita troca entre as gurias!', date: 'ABR 2025' },
]
</script>

<template>
  <section id="eventos-passados">
    <div class="container">
      <span class="section-tag" style="background:var(--pink); color:var(--blue);">Nossos encontros</span>
      <h2>Eventos que já aconteceram</h2>
      <p class="lead">Cada encontro é uma memória afetiva. Olha só o que já vivemos juntas!</p>

      <div class="gallery-scroll">
        <div v-for="e in eventos" :key="e.title" class="gallery-item">
          <div class="evt-icon">{{ e.icon }}</div>
          <h3>{{ e.title }}</h3>
          <p>{{ e.desc }}</p>
          <span class="evt-date">{{ e.date }}</span>
        </div>
      </div>
      <p class="scroll-hint">← deslize para ver mais →</p>
    </div>
  </section>
</template>
