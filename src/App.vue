<template>
  <div id="app" class="font-sans text-gray-800">
    <header class="border-t-4 border-blue-700 bg-white z-10 absolute w-full shadow-md">
      
      <nav class="container mx-auto px-8 flex flex-wrap justify-between items-center py-8">
        <div class="mb-0 lg:mb-6 xl:mb-0">
          <router-link :to="`/${$i18n.locale}`" class="font-bold text-xl flex items-end">
            <span>Bikeshop 4711</span>
          </router-link>
          

        </div>
        <div class="block lg:hidden">
          
        </div>
        <button class="flex items-center px-3 py-2 border rounded border-gray-500 hover:text-gray-600 hover:border-gray-600">
            {{ $t('cart') }}
          </button>
          <language-switcher />
      </nav>
    </header>
    <div class="bg-gray-100 min-h-screen pt-40 text-lg">
      <router-view/>
    </div>
  </div>
</template>

<script>
import LanguageSwitcher from '@/components/LanguageSwitcher.vue'


export default {
  name: 'app',
  components: {
    LanguageSwitcher,
  },
  data() {
    return {
      
    }
  },
  methods: {
    
  }
}
</script>

<style src="@/assets/css/tailwind.css" />


