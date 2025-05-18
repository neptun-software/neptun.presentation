---
layout: default
---

# Technische Umsetzung: Backend

<style>
.logo-container {
  background: white;
  border-radius: 24px;
  padding: 1.5rem;
  width: 220px;
  height: 220px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 2rem;
}
</style>

<div class="grid grid-cols-2 gap-16">
  <div>
    <div class="logo-container">
      <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='256' height='256' viewBox='0 0 256 256'%3E%3Cdefs%3E%3ClinearGradient id='logosNeonIcon0' x1='100%25' x2='12.069%25' y1='100%25' y2='0%25'%3E%3Cstop offset='0%25' stop-color='%2362f755'/%3E%3Cstop offset='100%25' stop-color='%238ff986' stop-opacity='0'/%3E%3C/linearGradient%3E%3ClinearGradient id='logosNeonIcon1' x1='100%25' x2='40.603%25' y1='100%25' y2='76.897%25'%3E%3Cstop offset='0%25' stop-opacity='0.9'/%3E%3Cstop offset='100%25' stop-color='%231a1a1a' stop-opacity='0'/%3E%3C/linearGradient%3E%3C/defs%3E%3Cpath fill='%2300e0d9' d='M0 44.139C0 19.762 19.762 0 44.139 0H211.86C236.238 0 256 19.762 256 44.139v142.649c0 25.216-31.915 36.16-47.388 16.256l-48.392-62.251v75.484c0 21.939-17.784 39.723-39.722 39.723h-76.36C19.763 256 0 236.238 0 211.861zm44.139-8.825a8.817 8.817 0 0 0-8.825 8.818v167.73c0 4.878 3.946 8.831 8.818 8.831h77.688c2.44 0 3.087-1.977 3.087-4.416v-101.22c0-25.222 31.914-36.166 47.395-16.255l48.391 62.243V44.14c0-4.879.455-8.825-4.416-8.825z'/%3E%3Cpath fill='url(%23logosNeonIcon0)' d='M0 44.139C0 19.762 19.762 0 44.139 0H211.86C236.238 0 256 19.762 256 44.139v142.649c0 25.216-31.915 36.16-47.388 16.256l-48.392-62.251v75.484c0 21.939-17.784 39.723-39.722 39.723h-76.36C19.763 256 0 236.238 0 211.861zm44.139-8.825a8.817 8.817 0 0 0-8.825 8.818v167.73c0 4.878 3.946 8.831 8.818 8.831h77.688c2.44 0 3.087-1.977 3.087-4.416v-101.22c0-25.222 31.914-36.166 47.395-16.255l48.391 62.243V44.14c0-4.879.455-8.825-4.416-8.825z'/%3E%3Cpath fill='url(%23logosNeonIcon1)' fill-opacity='0.4' d='M0 44.139C0 19.762 19.762 0 44.139 0H211.86C236.238 0 256 19.762 256 44.139v142.649c0 25.216-31.915 36.16-47.388 16.256l-48.392-62.251v75.484c0 21.939-17.784 39.723-39.722 39.723h-76.36C19.763 256 0 236.238 0 211.861zm44.139-8.825a8.817 8.817 0 0 0-8.825 8.818v167.73c0 4.878 3.946 8.831 8.818 8.831h77.688c2.44 0 3.087-1.977 3.087-4.416v-101.22c0-25.222 31.914-36.166 47.395-16.255l48.391 62.243V44.14c0-4.879.455-8.825-4.416-8.825z'/%3E%3Cpath fill='%2363f655' d='M211.861 0C236.238 0 256 19.762 256 44.139v142.649c0 25.216-31.915 36.16-47.388 16.256l-48.392-62.251v75.484c0 21.939-17.784 39.723-39.722 39.723a4.41 4.41 0 0 0 4.409-4.409V115.058c0-25.223 31.914-36.167 47.395-16.256l48.391 62.243V8.825c0-4.871-3.953-8.825-8.832-8.825'/%3E%3C/svg%3E" class="w-48" />
    </div>
    <h2 class="text-2xl font-bold mb-4">Datenbank</h2>
    <ul class="space-y-2">
      <li>PostgreSQL basiert</li>
      <li>Neon (Rust basiert): Serverless Postgres fork</li>
      <li>Hosting: Neon Serverless Cloud</li>
    </ul>
  </div>
  
  <div>
    <div class="logo-container">
      <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'%3E%3Cg fill='none'%3E%3Cg clip-path='url(%23unjsNitro4)'%3E%3Cpath fill='url(%23unjsNitro1)' fill-rule='evenodd' d='M28.173 5.616C22.438-1.107 12.34-1.907 5.617 3.828s-7.524 15.834-1.789 22.557s15.834 7.523 22.557 1.788s7.523-15.834 1.788-22.557m-7.97 8.398c.616 0 1.01.668.7 1.202l-.089.153l-6.038 9.935a.62.62 0 0 1-.529.297h-.576a.604.604 0 0 1-.585-.755l1.638-6.335a.8.8 0 0 0-.774-1h-2.517a.8.8 0 0 1-.774-1l2.472-9.565a.74.74 0 0 1 .716-.544q.061 0 .107.002h2.535a.8.8 0 0 1 .793.908l-.016.114l-.966 5.653a.8.8 0 0 0 .788.935z' clip-rule='evenodd'/%3E%3Cpath fill='url(%23unjsNitro2)' fill-rule='evenodd' d='M28.173 5.616C22.438-1.107 12.34-1.907 5.617 3.828s-7.524 15.834-1.789 22.557s15.834 7.523 22.557 1.788s7.523-15.834 1.788-22.557m-7.97 8.398c.616 0 1.01.668.7 1.202l-.089.153l-6.038 9.935a.62.62 0 0 1-.529.297h-.576a.604.604 0 0 1-.585-.755l1.638-6.335a.8.8 0 0 0-.774-1h-2.517a.8.8 0 0 1-.774-1l2.472-9.565a.74.74 0 0 1 .716-.544q.061 0 .107.002h2.535a.8.8 0 0 1 .793.908l-.016.114l-.966 5.653a.8.8 0 0 0 .788.935z' clip-rule='evenodd'/%3E%3Cmask id='unjsNitro0' width='32' height='33' x='0' y='0' maskUnits='userSpaceOnUse' style='mask-type:alpha'%3E%3Cpath fill='url(%23unjsNitro3)' d='M16 32.001c8.837 0 16-7.163 16-16s-7.163-16-16-16s-16 7.163-16 16s7.163 16 16 16'/%3E%3C/mask%3E%3Cg filter='url(%23unjsNitro5)' mask='url(%23unjsNitro0)'%3E%3Cpath fill='%23fff' d='M.89 10.741a16 16 0 1 0 30.365.434l-4.652 1.471a11.12 11.12 0 1 1-21.106-.3z'/%3E%3C/g%3E%3C/g%3E%3Cdefs%3E%3CradialGradient id='unjsNitro1' cx='0' cy='0' r='1' gradientTransform='matrix(31.2006 0 0 318.168 3.2 16)' gradientUnits='userSpaceOnUse'%3E%3Cstop stop-color='%2331b2f3'/%3E%3Cstop offset='.474' stop-color='%23f27cec'/%3E%3Cstop offset='1' stop-color='%23fd6641'/%3E%3C/radialGradient%3E%3CradialGradient id='unjsNitro2' cx='0' cy='0' r='1' gradientTransform='matrix(31.2006 0 0 318.168 3.2 16)' gradientUnits='userSpaceOnUse'%3E%3Cstop stop-color='%2331b2f3'/%3E%3Cstop offset='.474' stop-color='%23f27cec'/%3E%3Cstop offset='1' stop-color='%23fd6641'/%3E%3C/radialGradient%3E%3CradialGradient id='unjsNitro3' cx='0' cy='0' r='1' gradientTransform='matrix(31.2 0 0 318.162 3.2 16.001)' gradientUnits='userSpaceOnUse'%3E%3Cstop stop-color='%23f27cec'/%3E%3Cstop offset='.484' stop-color='%2331b2f3'/%3E%3Cstop offset='1' stop-color='%237d7573'/%3E%3C/radialGradient%3E%3CclipPath id='unjsNitro4'%3E%3Cpath fill='%23fff' d='M0 0h32v32H0z'/%3E%3C/clipPath%3E%3Cfilter id='unjsNitro5' width='52' height='41.26' x='-10' y='.741' color-interpolation-filters='sRGB' filterUnits='userSpaceOnUse'%3E%3CfeFlood flood-opacity='0' result='BackgroundImageFix'/%3E%3CfeBlend in='SourceGraphic' in2='BackgroundImageFix' result='shape'/%3E%3CfeGaussianBlur result='effect1_foregroundBlur_7_821' stdDeviation='5'/%3E%3C/filter%3E%3C/defs%3E%3C/g%3E%3C/svg%3E" class="w-48" />
    </div>
    <h2 class="text-2xl font-bold mb-4">Server</h2>
    <ul class="space-y-2">
      <li>Application: Nitro (Backend Server-Toolkit des Nuxt Meta-Frameworks)</li>
      <li>Hosting: Vercel Fluid Compute</li>
    </ul>
  </div>
</div>
