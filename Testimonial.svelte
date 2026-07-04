<script>
  /**
   * Props: stat, statLabel, quote, person, company, industry, bg
   */
  let { stat, statLabel, quote, person, company, industry, href = '#' } = $props();

  import { onMount } from 'svelte';
  let el;
  let visible = $state(false);
  onMount(() => {
    const obs = new IntersectionObserver(([e]) => { if (e.isIntersecting) visible = true; }, { threshold: 0.15 });
    obs.observe(el);
    return () => obs.disconnect();
  });
</script>

<div bind:this={el} class="bg-[#F8F9FF] border-y border-[#EAEAEA] py-12 sm:py-16">
  <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid sm:grid-cols-2 gap-10 items-center {visible ? 'fade-up visible' : 'fade-up'}">

      <!-- Stat -->
      <div>
        <div class="text-6xl sm:text-7xl font-bold text-[#3548FF] mb-2 tabular-nums">{stat}</div>
        <p class="text-lg font-semibold text-[#090909] mb-6">{statLabel}</p>
        <a href={href} class="text-sm font-semibold text-[#3548FF] hover:underline inline-flex items-center gap-1">
          Read full case study
          <svg width="14" height="14" viewBox="0 0 14 14" fill="none">
            <path d="M3 7h8M8 4l3 3-3 3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </a>
      </div>

      <!-- Quote -->
      <div>
        <svg class="w-8 h-8 text-[#3548FF] mb-4 opacity-30" fill="currentColor" viewBox="0 0 32 32">
          <path d="M10 8H4v8h6v8H4c0-6.627 0-12 6-12V8zm18 0h-6v8h6v8h-6c0-6.627 0-12 6-12V8z"/>
        </svg>
        <blockquote class="text-[#090909] text-base sm:text-lg leading-relaxed font-medium mb-6">
          "{quote}"
        </blockquote>
        <div class="flex items-center gap-3">
          <div class="w-9 h-9 rounded-full bg-[#EAEAEA] flex items-center justify-center text-sm font-bold text-[#090909]">
            {company[0]}
          </div>
          <div>
            <p class="text-sm font-semibold text-[#090909]">{person}</p>
            <p class="text-xs text-[#A5A5A5]">{company} · {industry}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
