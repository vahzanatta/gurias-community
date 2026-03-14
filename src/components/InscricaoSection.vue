<script setup>
import { ref } from 'vue'

const form = ref({ email: '', whatsapp: '', nome: '', curte: '', como: '', busca: '' })
const sent = ref(false)

function submit() {
  sent.value = true
  form.value = { email: '', whatsapp: '', nome: '', curte: '', como: '', busca: '' }
  setTimeout(() => sent.value = false, 5000)
}
</script>

<template>
  <section id="inscricao">
    <div class="container">
      <span class="section-tag" style="background:var(--pink-dark); color:var(--white);">Faça parte</span>
      <h2>Quero ser uma Guria!</h2>
      <p class="lead">Preencha o formulário abaixo e entre para a nossa comunidade. A gente mal pode esperar para te conhecer!</p>

      <div class="form-card">
        <Transition name="fade">
          <p v-if="sent" style="color:var(--pink); font-weight:800; margin-bottom:1rem;">
            🎉 Que alegria! Sua inscrição foi recebida. Fique de olho no e-mail!
          </p>
        </Transition>

        <form @submit.prevent="submit">
          <div class="form-group">
            <label for="insc-email">E-mail *</label>
            <input v-model="form.email" type="email" id="insc-email" placeholder="seu@email.com" required autocomplete="email" inputmode="email" />
          </div>
          <div class="form-group">
            <label for="insc-whatsapp">WhatsApp *</label>
            <input v-model="form.whatsapp" type="tel" id="insc-whatsapp" placeholder="(51) 99999-9999" required autocomplete="tel" inputmode="tel" />
          </div>
          <div class="form-group">
            <label for="insc-nome">Me conte mais de você *</label>
            <textarea v-model="form.nome" id="insc-nome" placeholder="Quem é você? Conta um pouco!" required style="min-height:80px;" />
          </div>
          <div class="form-group">
            <label for="insc-curte">O que tu curte?</label>
            <textarea v-model="form.curte" id="insc-curte" placeholder="Livros, séries, rolês, comida... tudo vale!" style="min-height:80px;" />
          </div>
          <div class="form-group">
            <label for="insc-como">Como achou a comunidade?</label>
            <select v-model="form.como" id="insc-como">
              <option value="">Selecione...</option>
              <option>Instagram</option>
              <option>Indicação de amiga</option>
              <option>WhatsApp</option>
              <option>Outro</option>
            </select>
          </div>
          <div class="form-group">
            <label for="insc-busca">O que você busca com a comunidade?</label>
            <textarea v-model="form.busca" id="insc-busca" placeholder="O que te trouxe até aqui? ✨" style="min-height:80px;" />
          </div>
          <p style="font-size:.8rem; color:rgba(255,255,255,.5); margin-bottom:1rem;">* Campos obrigatórios</p>
          <button type="submit" class="btn">Quero entrar! ✨</button>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active { transition: opacity .3s; }
.fade-enter-from, .fade-leave-to       { opacity: 0; }
</style>
