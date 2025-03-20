---
layout: none
---

<div id="url-container" class="url-container"></div>
<div id="centered-text" class="centered-text"></div>

<script setup>
import { onMounted, onUnmounted } from 'vue'

const props = defineProps({
  text: {
    type: String,
    default: 'Scraping'
  }
})

const baseUrls = [
  'https://docs.docker.com',
  'https://kubernetes.io/docs',
  'http://docs.github.com/en',
  'https://docs.gitlab.com/17.9',
  'https://helm.sh/docs',
  'https://kubevela.io/docs',
  'https://argo-cd.readthedocs.io/en/stable',
  'https://www.jenkins.io/doc',
  'https://docs.npmjs.com',
  'https://bun.sh/docs',
  'https://docs.deno.com',
  'https://packaging.python.org/en/latest',
  'https://sst.dev/docs',
  'https://coolify.io/docs',
  'https://docs.aws.amazon.com/en_us',
  'https://google.github.io/styleguide',
  'https://developer.mozilla.org/en-US',
  'https://www.radix-ui.com/primitives/docs',
  'https://www.radix-ui.com/themes/docs',
  'https://www.shadcn-vue.com/docs',
  'https://www.shadcn-svelte.com/docs',
  'https://ui.shadcn.com/docs',
  'https://iconify.design/docs',
  'https://www.typescriptlang.org/docs',
  'https://v3.tailwindcss.com/docs',
  'https://tailwindcss.com/docs',
  'https://sass-lang.com/documentation',
  'https://postcss.org/docs',
  'https://biomejs.dev/guides',
  'https://biomejs.dev/reference',
  'https://biomejs.dev/recipes',
  'https://biomejs.dev/internals',
  'https://biomejs.dev/analyzer',
  'https://biomejs.dev/formatter',
  'https://biomejs.dev/linter',
  'https://orm.drizzle.team/docs',
  'https://vite.dev/config',
  'https://vite.dev/guide',
  'https://v5.vite.dev/config',
  'https://v5.vite.dev/guide',
  'https://svelte.dev/docs/cli',
  'https://svelte.dev/docs/kit',
  'https://svelte.dev/docs/svelte',
  'https://svelte.dev/tutorial/svelte',
  'https://react.dev/reference',
  'https://react.dev/learn',
  'https://nitro.build/config',
  'https://nitro.build/deploy',
  'https://nitro.build/guide',
  'https://nuxt.com/docs',
  'https://nuxt.com/modules',
  'https://nuxt.com/deploy',
  'https://nuxt.com/blog',
  'https://vuejs.org/api',
  'https://vuejs.org/about',
  'https://vuejs.org/guide',
  'https://docs.astro.build/en',
  'https://astro.build/case-studies',
  'https://livewire.laravel.com/docs',
  'https://laravel.com/docs/12.x',
  'https://hono.dev',
  'https://elysiajs.com',
  'https://caddyserver.com/docs',
  'https://nektosact.com',
  'https://echo.labstack.com',
  'https://podman.io/docs',
  'https://goharbor.io/docs/2.12.0',
  'https://asdf-vm.com',
  'https://www.authelia.com',
  'https://better-auth.vercel.app/docs',
  'https://skaffold.dev/docs',
  'https://templ.guide',
  'https://frankenphp.dev/docs',
  'https://ktor.io/docs',
  'https://quarkus.io/guides',
  'https://fastapi.tiangolo.com',
  'https://docs.djangoproject.com/en/5.1',
  'https://flask.palletsprojects.com/en/stable',
  'https://docs.scrapy.org/en/latest',
  'https://docs.postalserver.io',
  'https://guides.rubyonrails.org',
  'https://api.rubyonrails.org',
  'https://hexdocs.pm/phoenix'
]

function fillScreen() {
  const container = document.getElementById('url-container')
  const centeredText = document.getElementById('centered-text')
  if (!container || !centeredText) return

  container.innerHTML = ''
  let text = ""
  
  // calculate how many times to repeat URLs to fill screen
  // start with a huge number and limit it in the DOM
  const totalChars = window.innerWidth * window.innerHeight / 50  // rough estimate of chars needed
  const baseText = baseUrls.join(' ')
  const repetitions = Math.ceil(totalChars / baseText.length) * 2
  
  for (let i = 0; i < repetitions; i++) {
    text += baseUrls.join(' ')
  }
  
  container.textContent = text
  centeredText.textContent = props.text
}

onMounted(() => {
  fillScreen()
  window.addEventListener('resize', fillScreen)
})

onUnmounted(() => {
  window.removeEventListener('resize', fillScreen)
})
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background-color: #020817;
}

.url-container {
  width: 100vw;
  height: 100vh;
  color: white;
  font-family: monospace;
  font-size: 8px;
  line-height: 1;
  background-color: #020817;
  overflow: hidden;
  padding: 0;
  margin: 0;
  word-break: break-all;
  text-align: justify;
  letter-spacing: -0.4px;
  position: relative;
}

.centered-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 8rem;
  font-weight: bold;
  z-index: 10;
  text-align: center;
}

.centered-text:empty {
  display: none;
}
</style>
