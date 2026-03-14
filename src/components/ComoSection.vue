<script setup>
const steps = [
  { n: 1, title: 'Preencha o formulário', desc: 'Conta um pouco sobre você lá na seção de inscrição. É rapidinho!' },
  { n: 2, title: 'Receba o acesso',       desc: 'Você receberá o link para entrar no grupo da comunidade.' },
  { n: 3, title: 'Se apresente',          desc: 'Conta quem você é e comece a se conectar com as outras gurias!' },
  { n: 4, title: 'Participe dos eventos', desc: 'Fique de olho na agenda e venha nos encontros todo mês.' },
]
</script>

<template>
  <section id="como">
    <div class="container">
      <span class="section-tag">Como funciona</span>
      <h2>Como entrar?</h2>
      <p class="lead">
        Pedimos uma taxa fixa mensal de <strong style="color:var(--blue)">R$20,00</strong>.
        Com esse valor compramos os materiais para os eventos — tintas, pincéis, guardanapos, jornais —
        e o que sobra é reinvestido na comunidade: coolers, térmicas e powerbanks para os rolês externos.
      </p>

      <div class="steps">
        <div v-for="step in steps" :key="step.n" class="step">
          <div class="step-num">{{ step.n }}</div>
          <div class="step-body">
            <h3>{{ step.title }}</h3>
            <p>{{ step.desc }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
