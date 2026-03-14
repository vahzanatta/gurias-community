<script setup>
import { onMounted } from 'vue'

// ► Cole aqui o seu Widget ID do behold.so
const BEHOLD_ID = ''

onMounted(() => {
  if (!BEHOLD_ID) return
  const script = document.createElement('script')
  script.src = 'https://w.behold.so/widget.js'
  script.type = 'module'
  document.head.appendChild(script)
  const el = document.createElement('behold-widget')
  el.setAttribute('feed-id', BEHOLD_ID)
  document.getElementById('behold-widget').appendChild(el)
})
</script>

<template>
  <section v-if="BEHOLD_ID" id="instagram">
    <div class="container">
      <span class="section-tag">Nossas redes</span>
      <h2>No Instagram</h2>
      <a href="https://instagram.com/guriascommunity" target="_blank" rel="noopener" class="ig-handle">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
          <rect x="2" y="2" width="20" height="20" rx="5" ry="5"/>
          <circle cx="12" cy="12" r="4"/>
          <circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/>
        </svg>
        @guriascommunity
      </a>
      <div id="behold-widget" />
    </div>
  </section>
</template>
