<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import TheNav           from './components/TheNav.vue'
import TheDrawer        from './components/TheDrawer.vue'
import BottomNav        from './components/BottomNav.vue'
import HeroSection      from './components/HeroSection.vue'
import SobreSection     from './components/SobreSection.vue'
import ComoSection      from './components/ComoSection.vue'
import EventosSection   from './components/EventosSection.vue'
import AgendaSection    from './components/AgendaSection.vue'
import InstagramSection from './components/InstagramSection.vue'
import SugestoesSection from './components/SugestoesSection.vue'
import InscricaoSection from './components/InscricaoSection.vue'
import TheFooter        from './components/TheFooter.vue'

const isDrawerOpen  = ref(false)
const activeSection = ref('sobre')

function toggleDrawer() { isDrawerOpen.value = !isDrawerOpen.value }
function closeDrawer()  { isDrawerOpen.value = false }

const sectionIds = ['sobre', 'como', 'eventos-passados', 'agenda', 'instagram', 'sugestoes', 'inscricao']
let observer = null

onMounted(() => {
  observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) activeSection.value = entry.target.id
    })
  }, { threshold: 0.35 })

  sectionIds.forEach(id => {
    const el = document.getElementById(id)
    if (el) observer.observe(el)
  })
})

onUnmounted(() => observer?.disconnect())
</script>

<template>
  <TheNav
    :is-drawer-open="isDrawerOpen"
    @toggle-drawer="toggleDrawer"
  />

  <TheDrawer
    :is-open="isDrawerOpen"
    @close="closeDrawer"
  />

  <HeroSection />
  <SobreSection />
  <ComoSection />
  <EventosSection />
  <AgendaSection />
  <InstagramSection />
  <SugestoesSection />
  <InscricaoSection />
  <TheFooter />

  <BottomNav :active-section="activeSection" />
</template>
