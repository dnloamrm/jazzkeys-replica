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

<style scoped>
.dock-navigation {
  position: fixed;
  bottom: 24px;
  left: 50%;
  transform: translateX(-50%);
  display: flex !important;
  align-items: center;
  justify-content: center;
  gap: 16px;
  z-index: 9999;
  visibility: visible !important;
  opacity: 1 !important;
}

.dock-btn {
  width: 64px;
  height: 64px;
  min-width: 64px;
  min-height: 64px;
  border-radius: 50%;
  border: none;
  background-color: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: transform 0.2s ease, background-color 0.2s ease;
  color: #ffffff;
}

.dock-btn:hover {
  transform: scale(1.08);
  background-color: rgba(255, 255, 255, 0.2);
}

.mdi-icon {
  width: 28px;
  height: 28px;
  fill: currentColor;
}
</style>
