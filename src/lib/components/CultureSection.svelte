<script lang="ts">
  const cards = [
    {
      title: "We Don't Chase Trends...",
      subtitle: "We Seek Timeless Beauty.",
      image: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?auto=format&fit=crop&q=80&w=800"
    },
    {
      title: "We Don't Add to the Noise...",
      subtitle: "We Create Quiet Spaces.",
      image: "https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&q=80&w=800"
    },
    {
      title: "We Don't Demand Your Time...",
      subtitle: "We Honor Your Attention.",
      image: "https://images.unsplash.com/photo-1518837695005-2083093ee35b?auto=format&fit=crop&q=80&w=800"
    }
  ];
</script>

<section class="py-24 px-6 md:px-12 bg-white">
  <div class="max-w-2xl mb-16">
    <p class="text-xl md:text-2xl leading-relaxed text-gray-800">
      In a world drowning in content, we believe in curation over abundance. Each essay is a carefully chosen refuge—a place where burnt-out professionals can find genuine peace, not just another distraction.
    </p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    {#each cards as card}
      <div class="group">
        <div class="aspect-[4/3] overflow-hidden rounded-lg mb-4 bg-gray-100">
          <img src={card.image} alt={card.title} class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition-all duration-500" />
        </div>
        <h3 class="text-sm text-gray-500 mb-1">{card.title}</h3>
        <p class="text-sm font-bold">{card.subtitle}</p>
        
        <div class="flex justify-between mt-4 text-xs text-gray-400">
           <span>→</span>
           <span>∞</span>
        </div>
      </div>
    {/each}
  </div>
</section>
