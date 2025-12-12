<script lang="ts">
  const themes = [
    "Wabi-Sabi",
    "Mono no Aware",
    "Saudade",
    "Hiraeth",
    "Sehnsucht"
  ];
</script>

<section class="relative min-h-screen flex flex-col justify-end pb-20 px-6 md:px-12 bg-gradient-to-b from-gray-950 via-gray-900 to-white text-[#1a1a1a]">
  <!-- Gradient overlay/background handling -->
  <div class="absolute inset-0 z-[-1] bg-[linear-gradient(180deg,#0a0a0a_0%,#1a1a1a_30%,#f5f5f5_70%,#fff_100%)]"></div>

  <div class="max-w-4xl mb-32 pt-40">
    <h1 class="text-3xl md:text-5xl font-medium leading-[1.15] tracking-tight">
      Contemplative escape through curated essays. <span class="text-gray-500">Discover mysterious beauty beyond daily chaos—five-minute cultural immersions for burnt-out professionals seeking mindful breaks.</span>
    </h1>
  </div>

  <div class="border-t border-gray-300 pt-8 flex flex-wrap gap-8 md:gap-16 items-center opacity-50">
    <p class="text-xs uppercase tracking-wider text-gray-600 font-medium">Explore themes:</p>
    {#each themes as theme}
      <div class="text-sm font-light text-gray-700">{theme}</div>
    {/each}
  </div>
</section>
