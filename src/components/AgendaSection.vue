<script setup>
const agenda = [
  { day: '22', month: 'Mar', title: 'Café com Gurias — Março',   desc: 'Encontro mensal de conexão e bate-papo entre as participantes.',                        badge: 'Presencial' },
  { day: '05', month: 'Abr', title: 'Roda de Conversa Online',   desc: '"Como criar conexões reais num mundo digital?" — Participe de onde estiver!',            badge: 'Online' },
  { day: '19', month: 'Abr', title: 'Workshop: Cuide-se, Guria!', desc: 'Tarde de bem-estar, autocuidado e troca de experiências entre as gurias.',              badge: 'Presencial' },
  { day: '10', month: 'Mai', title: 'Encontro Especial de Mães', desc: 'Celebração do Dia das Mães com um encontro especial para as mamães.',                    badge: 'Presencial' },
]
</script>

<template>
  <section id="agenda">
    <div class="container">
      <span class="section-tag">Próximos eventos</span>
      <h2>Agenda de eventos</h2>
      <p class="lead">Marque na agenda e não perca nenhum encontro!</p>

      <div class="agenda-list">
        <div v-for="item in agenda" :key="item.title" class="agenda-item">
          <div class="agenda-date">
            <div class="day">{{ item.day }}</div>
            <div class="month">{{ item.month }}</div>
          </div>
          <div class="agenda-info">
            <h3>{{ item.title }}</h3>
            <p>{{ item.desc }}</p>
            <span class="agenda-badge">{{ item.badge }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
