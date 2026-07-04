<script>
  import { onMount } from 'svelte';

  // The exact Bluecopa headline for this section
  const headline = 'Build the AI-powered finance intelligence engine for your enterprise';
  const chars = headline.split('');

  let litCount = $state(0);
  let sectionEl;
  let animating = false;

  onMount(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting && !animating) {
          animating = true;
          // Animate characters one by one with stagger of 14ms (matching Bluecopa's 0.014s)
          chars.forEach((_, i) => {
            setTimeout(() => {
              litCount = i + 1;
            }, i * 22);
          });
        }
      },
      { threshold: 0.2, rootMargin: '0px 0px -80px 0px' }
    );
    observer.observe(sectionEl);
    return () => observer.disconnect();
  });
</script>

<section bind:this={sectionEl} class="py-20 sm:py-28 bg-white">
  <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
    <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold leading-[1.15] tracking-[-1px]" aria-label={headline}>
      {#each chars as char, i}
        {#if char === ' '}
          <span class="wave-char {i < litCount ? 'lit' : ''}">&nbsp;</span>
        {:else}
          <span class="wave-char {i < litCount ? 'lit' : ''}">{char}</span>
        {/if}
      {/each}
    </h2>
  </div>
</section>
