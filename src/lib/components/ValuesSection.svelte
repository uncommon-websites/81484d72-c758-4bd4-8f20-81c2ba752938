<script lang="ts">
  const photos = [
    {
      title: "Break the Doomscroll",
      desc: "Replace mindless scrolling with mindful reading. Each essay offers a genuine escape from the chaos.",
      img: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?auto=format&fit=crop&q=80&w=400"
    },
    {
      title: "Find Your Calm",
      desc: "Discover tranquility in curated moments of beauty. Five minutes that restore rather than drain your energy.",
      img: "https://images.unsplash.com/photo-1501139083538-0139583c060f?auto=format&fit=crop&q=80&w=400"
    },
    {
      title: "Cultivate Awareness",
      desc: "Learn to see art amongst the patterns of daily life. Carry contemplative wisdom into your everyday moments.",
      img: "https://images.unsplash.com/photo-1518837695005-2083093ee35b?auto=format&fit=crop&q=80&w=400"
    }
  ];
</script>

<section class="py-24 px-6 md:px-12 bg-white">
  <div class="max-w-xl mb-16">
    <h3 class="text-lg font-bold mb-2">We focus on your peace, not just content.</h3>
    <p class="text-gray-500 text-sm leading-relaxed">
      In a world of endless notifications and demands, we create intentional pauses. Our essays are designed for burnt-out professionals who crave mindful breaks—spaces where you can breathe, reflect, and reconnect with what matters.
    </p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    {#each photos as photo}
      <div>
        <div class="aspect-[3/4] rounded-lg overflow-hidden mb-4 bg-gray-100">
          <img src={photo.img} alt={photo.title} class="w-full h-full object-cover" />
        </div>
        <h4 class="text-xs font-bold mb-1">{photo.title}</h4>
        <p class="text-[10px] text-gray-500 leading-relaxed">{photo.desc}</p>
      </div>
    {/each}
  </div>
</section>
