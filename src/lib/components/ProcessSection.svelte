<script lang="ts">
  import { onMount } from 'svelte';

  const steps = [
    {
      id: "discover",
      title: "Discover Hidden Beauty",
      text: "Every essay begins with finding the extraordinary in the ordinary. We seek out moments of profound beauty that exist beyond language—the kind that makes you pause, breathe, and see the world differently.",
      tags: ["Cultural Exploration", "Aesthetic Philosophy", "Mindful Observation", "Pattern Recognition", "Emotional Resonance", "Timeless Wisdom"],
      graphic: "lines"
    },
    {
      id: "curate",
      title: "Curate Contemplative Moments",
      text: "Not every beautiful thing deserves your attention. We carefully select essays that offer genuine depth and meaning, filtering out noise to bring you only what truly matters for your mindful break.",
      tags: ["Quality Selection", "Thematic Coherence", "Emotional Depth", "Cultural Context", "Accessibility", "Timeless Relevance"],
      graphic: "curve"
    },
    {
      id: "immerse",
      title: "Immerse in Tranquility",
      text: "Each essay is crafted as a five-minute escape—a portal to contemplative spaces where you can find peace. We blend evocative imagery, thoughtful prose, and cultural insights into experiences that restore rather than drain.",
      tags: ["Visual Storytelling", "Poetic Language", "Atmospheric Design", "Pacing & Rhythm", "Sensory Details", "Emotional Journey"],
      graphic: "circle-top"
    },
    {
      id: "reflect",
      title: "Reflect and Reconnect",
      text: "The true value emerges after reading. Our essays plant seeds of awareness that continue growing, helping you find art amongst the patterns of daily life and reconnect with what matters most.",
      tags: ["Lasting Impact", "Personal Meaning", "Mindful Living", "Perspective Shift", "Inner Peace", "Daily Practice"],
      graphic: "circle-waves"
    }
  ];

  let activeStep = 0;
  let sectionRef: HTMLElement;

  onMount(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            const index = steps.findIndex(step => step.id === entry.target.id);
            if (index !== -1) {
              activeStep = index;
            }
          }
        });
      },
      {
        root: null,
        rootMargin: "-20% 0px -20% 0px", // Trigger when element is in the middle 60% of viewport
        threshold: 0.5
      }
    );

    steps.forEach((step) => {
      const el = document.getElementById(step.id);
      if (el) observer.observe(el);
    });

    return () => observer.disconnect();
  });
</script>

<section class="bg-gray-950 text-white py-24 px-6 md:px-12 relative" bind:this={sectionRef}>
  <div class="max-w-screen-2xl mx-auto flex flex-col md:flex-row gap-12">
    
    <!-- Sticky Navigation -->
    <div class="md:w-1/2 md:h-[calc(100vh-6rem)] md:sticky md:top-24 flex flex-col justify-center">
      <div class="space-y-8">
        {#each steps as step, i}
          <div class="transition-opacity duration-500 {i === activeStep ? 'opacity-100' : 'opacity-30'}">
            <p class="text-xl md:text-2xl font-light mb-1">Our approach to</p>
            <h2 class="text-2xl md:text-3xl font-bold">{step.title}</h2>
          </div>
        {/each}
      </div>
    </div>

    <!-- Scrollable Cards -->
    <div class="md:w-1/2 space-y-24 pt-12 md:pt-0">
      {#each steps as step, i}
        <div class="bg-white text-black rounded-lg p-8 md:p-12 min-h-[600px] flex flex-col justify-between scroll-mt-32" id={step.id}>
          <!-- Graphic Placeholder -->
          <div class="flex-1 flex items-center justify-center mb-8 border border-gray-100 rounded bg-gray-50 min-h-[200px]">
             {#if step.graphic === 'lines'}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <line x1="20" y1="20" x2="20" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="40" y1="20" x2="40" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="60" y1="20" x2="60" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="80" y1="20" x2="80" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="100" y1="20" x2="100" y2="80" stroke="black" stroke-width="1"/>
                </svg>
             {:else if step.graphic === 'curve'}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <path d="M20 80 Q 100 0 180 80" fill="none" stroke="black" stroke-width="1"/>
                </svg>
             {:else if step.graphic === 'circle-top'}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <circle cx="100" cy="100" r="60" fill="none" stroke="black" stroke-width="1"/>
                    <circle cx="100" cy="100" r="40" fill="none" stroke="black" stroke-width="1"/>
                </svg>
             {:else}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <ellipse cx="100" cy="50" rx="80" ry="20" fill="none" stroke="black" stroke-width="1"/>
                    <ellipse cx="100" cy="50" rx="60" ry="15" fill="none" stroke="black" stroke-width="1"/>
                    <ellipse cx="100" cy="50" rx="40" ry="10" fill="none" stroke="black" stroke-width="1"/>
                </svg>
             {/if}
          </div>

          <div>
             <p class="text-lg leading-relaxed mb-8">{step.text}</p>

             <div class="grid grid-cols-2 gap-4 text-xs font-medium text-gray-600">
               {#each step.tags as tag}
                 <div class="flex items-center gap-2">
                   <span class="w-1.5 h-1.5 bg-black rounded-full shrink-0"></span>
                   {tag}
                 </div>
               {/each}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
