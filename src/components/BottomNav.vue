<script setup>
defineProps({ activeSection: String })

const tabs = [
  { href: '#sobre',            section: 'sobre',            icon: '💜', label: 'Sobre' },
  { href: '#como',             section: 'como',             icon: '👋', label: 'Como' },
  { href: '#eventos-passados', section: 'eventos-passados', icon: '🎉', label: 'Eventos' },
  { href: '#agenda',           section: 'agenda',           icon: '🗓️', label: 'Agenda' },
  { href: '#inscricao',        section: 'inscricao',        icon: '✨', label: 'Entrar' },
]
</script>

<template>
  <nav class="bottom-nav" aria-label="Navegação principal">
    <a
      v-for="tab in tabs"
      :key="tab.href"
      :href="tab.href"
      class="tab"
      :class="{ active: activeSection === tab.section }"
    >
      <span class="tab-icon">{{ tab.icon }}</span>
      {{ tab.label }}
    </a>
  </nav>
</template>
