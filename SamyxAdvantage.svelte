<script>
  import { onMount } from 'svelte';

  const stats = [
    { value: 70, suffix: '%', label: 'Faster close' },
    { value: 100, suffix: '%', label: 'Data accuracy' },
    { value: 50, suffix: '%', label: 'Lower costs' },
  ];

  let counts = $state([0, 0, 0]);
  let started = $state(false);
  let sectionEl;

  onMount(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting && !started) {
          started = true;
          stats.forEach((s, i) => {
            const duration = 1200;
            const steps = 60;
            const increment = s.value / steps;
            let current = 0;
            const timer = setInterval(() => {
              current = Math.min(current + increment, s.value);
              counts[i] = Math.round(current);
              if (current >= s.value) clearInterval(timer);
            }, duration / steps);
          });
        }
      },
      { threshold: 0.4 }
    );
    observer.observe(sectionEl);
    return () => observer.disconnect();
  });
</script>

<section bind:this={sectionEl} class="blue-section-bg py-16 sm:py-20">
  <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">

    <!-- Section label -->
    <p class="text-center text-sm font-semibold text-white/60 uppercase tracking-widest mb-12">
      The SamyxAI advantage
    </p>

    <div class="grid grid-cols-1 sm:grid-cols-3 gap-8 sm:gap-0 sm:divide-x sm:divide-white/20">
      {#each stats as stat, i}
        <div class="text-center px-8">
          <div class="text-5xl sm:text-6xl font-bold text-white mb-2 tabular-nums">
            {counts[i]}{stat.suffix}
          </div>
          <p class="text-base font-medium text-white/70">{stat.label}</p>
        </div>
      {/each}
    </div>
  </div>
</section>
