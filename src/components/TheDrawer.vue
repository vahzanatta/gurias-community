<script setup>
defineProps({ isOpen: Boolean })
defineEmits(['close'])

const links = [
  { href: '#sobre',            icon: '💜', label: 'Sobre' },
  { href: '#como',             icon: '👋', label: 'Como funciona' },
  { href: '#eventos-passados', icon: '🎉', label: 'Eventos' },
  { href: '#agenda',           icon: '🗓️', label: 'Agenda' },
  { href: '#sugestoes',        icon: '💡', label: 'Sugestões' },
]
</script>

<template>
  <div>
    <div
      class="drawer-overlay"
      :class="{ open: isOpen }"
      @click="$emit('close')"
    />
    <div class="drawer" :class="{ open: isOpen }">
      <nav>
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          @click="$emit('close')"
        >
          <span class="nav-icon">{{ link.icon }}</span> {{ link.label }}
        </a>
      </nav>
      <a href="#inscricao" class="drawer-cta" @click="$emit('close')">
        Quero entrar! ✨
      </a>
    </div>
  </div>
</template>
