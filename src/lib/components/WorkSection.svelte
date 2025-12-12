<script lang="ts">
  const essays = [
    {
      title: "The Art of Imperfection",
      desc: "Finding beauty in the weathered, the worn, and the incomplete.",
      bg: "bg-gray-950",
      img: "", 
      dark: true,
      theme: "Wabi-Sabi"
    },
    {
      title: "Fleeting Moments",
      desc: "The bittersweet awareness of transience in cherry blossoms.",
      bg: "bg-gray-100",
      img: "https://images.unsplash.com/photo-1522383225653-ed111181a951?auto=format&fit=crop&q=80&w=800",
      dark: false,
      theme: "Mono no Aware"
    },
    {
      title: "Longing for Home",
      desc: "The melancholic yearning for a place that may never have existed.",
      bg: "bg-gray-200",
      img: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?auto=format&fit=crop&q=80&w=800",
      dark: false,
      theme: "Hiraeth"
    },
    {
      title: "Silent Spaces",
      desc: "Discovering profound meaning in emptiness and negative space.",
      bg: "bg-black",
      img: "",
      dark: true,
      theme: "Ma"
    },
    {
      title: "The Poetry of Rain",
      desc: "Finding tranquility in the rhythm of water meeting earth.",
      bg: "bg-gray-50",
      img: "https://images.unsplash.com/photo-1428908728789-d2de25dbd4e2?auto=format&fit=crop&q=80&w=800",
      dark: false,
      full: true,
      theme: "Contemplation"
    },
    {
      title: "Ancient Pathways",
      desc: "Walking meditation through forgotten trails and timeless wisdom.",
      bg: "bg-gray-100",
      img: "https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&q=80&w=800",
      dark: false,
      theme: "Journey"
    },
    {
      title: "Moonlight Reflections",
      desc: "The mysterious beauty that emerges when day surrenders to night.",
      bg: "bg-gray-900",
      img: "https://images.unsplash.com/photo-1494500764479-0c8f2919a3d8?auto=format&fit=crop&q=80&w=800",
      dark: true,
      theme: "Yūgen"
    }
  ];
</script>

<section class="px-6 md:px-12 py-24 bg-white">
  <div class="max-w-3xl mb-16">
    <h2 class="text-2xl md:text-3xl font-medium leading-tight">
      <span class="font-bold">Curated essays exploring mysterious beauty</span> that transcends words—each piece offers a five-minute escape into contemplative spaces beyond the daily chaos.
    </h2>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-12">
    {#each essays as essay}
      <div class="group cursor-pointer {essay.full ? 'md:col-span-2' : ''}">
        <div class={`aspect-[4/3] w-full rounded-lg overflow-hidden relative ${essay.bg} mb-4 ${essay.full ? 'md:aspect-[2.5/1]' : ''}`}>
          {#if essay.img}
             <img src={essay.img} alt={essay.title} class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105" />
          {:else}
             <div class="w-full h-full flex items-center justify-center">
                <span class={`text-xl font-light tracking-wide ${essay.dark ? 'text-white' : 'text-black'}`}>{essay.theme}</span>
             </div>
          {/if}
        </div>
        <h3 class="text-sm font-bold mb-1">{essay.title}</h3>
        <p class="text-sm text-gray-600">{essay.desc}</p>
      </div>
    {/each}
  </div>
</section>
