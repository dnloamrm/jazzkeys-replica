<template>
  <nav class="dock-navigation">
    <button 
      v-for="(item, index) in navItems" 
      :key="index" 
      class="dock-btn"
      :aria-label="item.label"
      @click="item.action"
    >
      <svg class="mdi-icon" viewBox="0 0 24 24">
        <path :d="item.icon" />
      </svg>
    </button>
  </nav>
</template>

<script setup>
import { 
  mdiPlay, 
  mdiPlus, 
  mdiMusicNote, 
  mdiShareVariant, 
  mdiWeatherSunny, 
  mdiInformationOutline 
} from '@mdi/js'

const navItems = [
  { label: 'Play', icon: mdiPlay, action: () => console.log('Play') },
  { label: 'Adicionar', icon: mdiPlus, action: () => console.log('Add') },
  { label: 'Áudio', icon: mdiMusicNote, action: () => console.log('Audio') },
  { label: 'Partilhar', icon: mdiShareVariant, action: () => console.log('Share') },
  { label: 'Tema', icon: mdiWeatherSunny, action: () => console.log('Theme') },
  { label: 'Info', icon: mdiInformationOutline, action: () => console.log('Info') },
]
</script>

<style>
/* Força a visibilidade global sem scoped para sobrepor a introdução */
.dock-navigation {
  position: fixed !important;
  bottom: 24px !important;
  left: 50% !important;
  transform: translateX(-50%) !important;
  display: flex !important;
  align-items: center !important;
  justify-content: center !important;
  gap: 16px !important;
  z-index: 2147483647 !important; /* Valor máximo de z-index para ficar sempre no topo */
  visibility: visible !important;
  opacity: 1 !important;
  pointer-events: auto !important;
}

.dock-btn {
  width: 64px !important;
  height: 64px !important;
  min-width: 64px !important;
  min-height: 64px !important;
  border-radius: 50% !important;
  border: none !important;
  background-color: rgba(255, 255, 255, 0.15) !important;
  backdrop-filter: blur(10px) !important;
  -webkit-backdrop-filter: blur(10px) !important;
  display: flex !important;
  align-items: center !important;
  justify-content: center !important;
  cursor: pointer !important;
  transition: transform 0.2s ease, background-color 0.2s ease !important;
  color: #ffffff !important;
}

.dock-btn:hover {
  transform: scale(1.08) !important;
  background-color: rgba(255, 255, 255, 0.25) !important;
}

.mdi-icon {
  width: 28px !important;
  height: 28px !important;
  fill: currentColor !important;
}
</style>
