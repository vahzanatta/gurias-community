<script setup>
import { ref } from 'vue'

const nome = ref('')
const tipo = ref('')
const msg  = ref('')
const sent = ref(false)

function submit() {
  sent.value = true
  nome.value = ''
  tipo.value = ''
  msg.value  = ''
  setTimeout(() => sent.value = false, 4000)
}
</script>

<template>
  <section id="sugestoes">
    <div class="container">
      <span class="section-tag">Sua voz importa</span>
      <h2>Espaço para sugestões</h2>
      <p class="lead">A comunidade é feita por todas nós. Tem uma ideia, feedback ou sugestão? Conta pra gente!</p>

      <div class="form-card">
        <Transition name="fade">
          <p v-if="sent" style="color:var(--pink-dark); font-weight:800; margin-bottom:1rem;">
            💜 Obrigada! Sua sugestão foi recebida com muito carinho.
          </p>
        </Transition>

        <form @submit.prevent="submit">
          <div class="form-group">
            <label for="sug-nome">Seu nome</label>
            <input v-model="nome" type="text" id="sug-nome" placeholder="Como você se chama?" required autocomplete="name" />
          </div>
          <div class="form-group">
            <label for="sug-tipo">Tipo de sugestão</label>
            <select v-model="tipo" id="sug-tipo">
              <option value="">Selecione...</option>
              <option>Ideia de evento</option>
              <option>Tema para roda de conversa</option>
              <option>Melhoria na comunidade</option>
              <option>Outro</option>
            </select>
          </div>
          <div class="form-group">
            <label for="sug-msg">Sua sugestão</label>
            <textarea v-model="msg" id="sug-msg" placeholder="Conta tudo! Toda ideia é bem-vinda 💜" required />
          </div>
          <button type="submit" class="btn btn-pink">Enviar sugestão</button>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active { transition: opacity .3s; }
.fade-enter-from, .fade-leave-to       { opacity: 0; }
</style>
