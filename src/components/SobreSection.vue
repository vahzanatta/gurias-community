<script setup>
const features = [
  { icon: '📚', title: 'Clube do livro',             desc: 'Encontro fixo todo mês para discutir leituras e trocar perspectivas entre as gurias.' },
  { icon: '🥂', title: 'Happy Hour mensal',          desc: 'Local escolhido pelas aniversariantes do mês — porque celebrar junto é melhor!' },
  { icon: '🎨', title: 'Pintura de taças e ecobags', desc: 'Atividade criativa fixa todo mês. Vem criar, relaxar e se conectar!' },
  { icon: '🩺', title: 'Meetings com profissionais', desc: 'Nutricionista, psicóloga e mais — espaço para tirar dúvidas com quem entende.' },
  { icon: '📍', title: 'Eventos por toda POA',       desc: 'Rolês por Porto Alegre e região sugeridos pelas próprias gurias da comunidade.' },
]
</script>

<template>
  <section id="sobre">
    <div class="container">
      <span class="section-tag">O que é a comunidade</span>
      <h2>Um lugar feito para você, guria!</h2>
      <p class="lead">Conexões reais com mulheres que querem o mesmo que você. Liberdade para participar quando e onde quiser.</p>

      <div class="sobre-inner">
        <div class="sobre-logo">
          <img src="/Logo.png" alt="Gurias Community" />
        </div>

        <div class="sobre-cards">
          <div v-for="f in features" :key="f.title" class="card-feature">
            <div class="icon">{{ f.icon }}</div>
            <div>
              <h3>{{ f.title }}</h3>
              <p>{{ f.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
