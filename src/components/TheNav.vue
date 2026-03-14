<script setup>
defineProps({
  isDrawerOpen: Boolean,
})
defineEmits(['toggle-drawer'])

const links = [
  { href: '#sobre',            label: 'Sobre' },
  { href: '#como',             label: 'Como funciona' },
  { href: '#eventos-passados', label: 'Eventos' },
  { href: '#agenda',           label: 'Agenda' },
  { href: '#sugestoes',        label: 'Sugestões' },
]
</script>

<template>
  <header class="topnav">
    <img src="/Logo.png" alt="Gurias Community" class="topnav-logo" />

    <div class="desktop-links">
      <a v-for="link in links" :key="link.href" :href="link.href">{{ link.label }}</a>
      <a href="#inscricao" class="nav-cta">Quero entrar!</a>
    </div>

    <button
      class="hamburger"
      :class="{ open: isDrawerOpen }"
      aria-label="Abrir menu"
      @click="$emit('toggle-drawer')"
    >
      <span /><span /><span />
    </button>
  </header>
</template>
