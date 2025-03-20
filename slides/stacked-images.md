<div class="folder-stack">
  <div 
    v-for="(url, index) in reversedImageUrls" 
    :key="index"
    class="folder-item"
    :style="{
      zIndex: index + 1,
      width: `${100 - (index * 3)}%`,
      transform: `translateY(${index * 30}px)`,
      maxHeight: '70vh'
    }"
  >
    <img :src="url" class="folder-image" />
  </div>
</div>

<script setup>
import { ref, computed } from 'vue'

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

// Reverse the array to put fetcher at the bottom
const reversedImageUrls = computed(() => [...imageUrls].reverse())
</script>
<style scoped>
.folder-stack {
  width: 100%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding-top: 10px;
  padding-bottom: 300px;
  background-color: #020817;
}
.folder-item {
  position: absolute;
  max-width: 900px;
  width: 90%;
  border-radius: 8px;
  background: linear-gradient(to bottom, #4ade80, #22d3ee);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
  overflow: hidden;
}
.folder-item:hover {
  transform: translateY(-10px) !important;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
  z-index: 999 !important;
}
.folder-image {
  width: 100%;
  height: auto;
  display: block;
  object-position: top;
  object-fit: cover;
}
</style>