<script>
  import { Check, Palette } from 'lucide-svelte';
</script>

<slot />

<div class="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 flex items-center justify-center p-4">
  <div class="bg-white rounded-lg shadow-xl p-8 max-w-md text-center">
    <div class="flex justify-center gap-4 mb-6">
      <Check class="w-12 h-12 text-green-500" />
      <Palette class="w-12 h-12 text-indigo-500" />
    </div>
    <h1 class="text-3xl font-bold text-gray-900 mb-2">
      ¡Ambiente listo! 🚀
    </h1>
    <p class="text-gray-600 mb-4">
      SvelteKit 5 + Tailwind CSS + Lucide Icons
    </p>
    <div class="flex gap-2 justify-center text-sm">
      <span class="px-3 py-1 bg-orange-100 text-orange-700 rounded-full">SvelteKit</span>
      <span class="px-3 py-1 bg-blue-100 text-blue-700 rounded-full">Tailwind</span>
      <span class="px-3 py-1 bg-purple-100 text-purple-700 rounded-full">Lucide</span>
    </div>
  </div>
</div>