<script lang="ts">
  const stats = [
    {
      label: "100K Subscribers",
      desc: "Our growing community of mindfulness seekers finds refuge in curated tranquility. Each subscriber represents someone choosing contemplation over doomscrolling, seeking meaning beyond the daily chaos.",
      img: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?auto=format&fit=crop&q=80&w=200"
    },
    {
      label: "5-Minute Reads",
      desc: "Every essay is crafted for the perfect mindful break. Long enough to transport you to contemplative spaces, short enough to fit into your busy day—a cultural immersion that respects your time.",
      img: "https://images.unsplash.com/photo-1501139083538-0139583c060f?auto=format&fit=crop&q=80&w=200"
    },
    {
      label: "$4.2B Market",
      desc: "We're capturing the wellness content market with a unique approach—not meditation apps or productivity hacks, but genuine cultural exploration that feeds the soul and quiets the mind.",
      img: "https://images.unsplash.com/photo-1518837695005-2083093ee35b?auto=format&fit=crop&q=80&w=200"
    },
    {
      label: "Founded by Jon Lexa",
      desc: "Jon experienced the struggle of seeking meaning beyond daily chaos firsthand. His unique perspective on mindful content curation comes from years of finding art amongst the patterns of modern life.",
      img: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&q=80&w=200"
    }
  ];
</script>

<section class="py-24 px-6 md:px-12 bg-white border-t border-gray-100">
  <div class="mb-16">
    <p class="text-gray-500 max-w-xl">
      Curious about our journey? Here's a glimpse into what makes Yugen Today a sanctuary for burnt-out professionals seeking mindful moments.
    </p>
  </div>

  <div class="space-y-16">
    {#each stats as stat}
      <div class="flex flex-col md:flex-row md:items-start justify-between gap-8 border-b border-gray-100 pb-16 last:border-0">
        <h3 class="text-2xl md:text-4xl font-medium w-full md:w-1/3">{stat.label}</h3>
        <div class="w-full md:w-1/3">
           <p class="text-xs leading-relaxed text-gray-500">{stat.desc}</p>
        </div>
        <div class="w-full md:w-1/6 flex justify-end">
           <img src={stat.img} alt={stat.label} class="w-20 h-20 object-cover rounded bg-gray-100" />
        </div>
      </div>
    {/each}
  </div>
</section>
