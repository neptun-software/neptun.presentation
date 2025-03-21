<h1 class="text-center">Repositories</h1>

<div class="folder-stack">
  <div
    v-for="(url, index) in reversedImageUrls"
    :key="index"
    class="folder-item"
    :style="{
      'z-index': index + 1,
      'width': `${95 - (index * 4)}%`,
      'transform': `translateY(${index * 20}px)`
    }"
    @mouseenter="e => handleHover(e, index)"
    @mouseleave="e => handleLeave(e, index)"
    @click="showFullscreen(url)"
  >
    <img :src="url" class="folder-image" />
  </div>
</div>

<div v-if="fullscreenImage" class="fullscreen-overlay" @click="closeFullscreen">
  <div class="fullscreen-container">
    <button class="close-button" @click="closeFullscreen">×</button>
    <img :src="fullscreenImage" class="fullscreen-image" @click.stop />
  </div>
</div>

<script setup>
import { computed, ref } from 'vue'

const fullscreenImage = ref(null)

const imageUrls = [
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/github.repository.fetcher.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.scraper.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.data.generators.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.ai.scraper.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.github.app.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.ai.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.tools.docs.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.cli.png',
  'https://raw.githubusercontent.com/neptun-software/neptun.identity/refs/heads/main/repositories/neptun.web.png'
]

const reversedImageUrls = computed(() => [...imageUrls].reverse())

const handleHover = (e, index) => {
  const el = e.currentTarget
  el.style.transform = `translateY(${(index * 20) - 20}px)`
  el.style.zIndex = '999'
}

const handleLeave = (e, index) => {
  const el = e.currentTarget
  el.style.transform = `translateY(${index * 20}px)`
  el.style.zIndex = String(index + 1)
}

const showFullscreen = (url) => {
  fullscreenImage.value = url
}

const closeFullscreen = () => {
  fullscreenImage.value = null
}
</script>

<style scoped>
.folder-stack {
  width: 100%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  background-color: #020817;
  min-height: 100vh;
}

.folder-item {
  position: absolute;
  max-width: 1200px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
  overflow: hidden;
  cursor: pointer;
}

.folder-item:hover {
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}

.folder-image {
  width: 100%;
  height: auto;
  display: block;
  object-position: top;
  object-fit: contain;
}

.fullscreen-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.9);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}

.fullscreen-container {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.fullscreen-image {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
  margin: auto;
}

.close-button {
  position: fixed;
  aspect-ratio: 1;
  top: 10px;
  right: 10px;
  height: 20px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  border: none;
  color: white;
  font-size: 18px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.3s ease;
  z-index: 10000;
}

.close-button:hover {
  background: rgba(255, 255, 255, 0.3);
}
</style>
