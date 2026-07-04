<script>
  import { onMount } from 'svelte';
  let sectionEl;
  let visible = $state(false);
  onMount(() => {
    const obs = new IntersectionObserver(([e]) => { if (e.isIntersecting) visible = true; }, { threshold: 0.2 });
    obs.observe(sectionEl);
    return () => obs.disconnect();
  });
</script>

<section bind:this={sectionEl} class="py-20 sm:py-28 relative overflow-hidden border-t border-[#EAEAEA]">

  <!-- Background pattern matching Bluecopa final-cta-background feel -->
  <div class="absolute inset-0 pointer-events-none"
    style="background: radial-gradient(ellipse 80% 60% at 50% 50%, #EEF0FF 0%, #fff 70%);">
  </div>
  <div class="absolute inset-0 pointer-events-none"
    style="background-image: radial-gradient(#3548FF14 1px, transparent 1px); background-size: 28px 28px;">
  </div>

  <div class="relative max-w-3xl mx-auto px-4 sm:px-6 text-center">
    <div class="{visible ? 'fade-up visible' : 'fade-up'}">
      <p class="text-xs font-bold text-[#3548FF] uppercase tracking-widest mb-4">Ready to get started?</p>
      <h2 class="text-3xl sm:text-5xl font-bold text-[#090909] tracking-tight leading-tight mb-6">
        Future-proof your finance<br/>operations, today
      </h2>
      <p class="text-[#A5A5A5] text-lg mb-10 max-w-xl mx-auto">
        Join finance teams at Yatra, EkaCare, Diversey, and 50+ enterprises who've automated their operations with Bluecopa.
      </p>
      <div class="flex flex-col sm:flex-row items-center justify-center gap-3">
        <a
          href="/demo"
          class="px-8 py-3.5 text-base font-semibold text-white bg-[#3548FF] hover:bg-[#1a2bcc] rounded-lg shadow-md hover:shadow-xl transition-all duration-200"
        >
          Book a demo
        </a>
        <a
          href="/samyxai"
          class="px-8 py-3.5 text-base font-medium text-[#090909] border border-[#EAEAEA] hover:border-[#3548FF]/40 rounded-lg transition-all"
        >
          Learn more about SamyxAI™
        </a>
      </div>
    </div>
  </div>
</section>
