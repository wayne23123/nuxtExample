npm run dev

package.json 看 nuxt version

介紹 /modules

安裝 tailwindcss

npm install --save-dev @nuxtjs/tailwindcss

and then to the modules section of nuxt.config.{ts,js}

export default defineNuxtConfig({
modules: [
'@nuxtjs/tailwindcss'
]
})
