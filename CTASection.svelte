<script>
  let email = $state('');
  let submitted = $state(false);

  function handleSubmit(e) {
    e.preventDefault();
    if (email) submitted = true;
  }
</script>

<section id="demo" class="py-24 bg-gradient-to-br from-indigo-600 via-indigo-700 to-violet-700 relative overflow-hidden">

  <!-- Background shapes -->
  <div class="absolute inset-0 pointer-events-none">
    <div class="absolute -top-24 -right-24 w-96 h-96 bg-white/5 rounded-full"></div>
    <div class="absolute -bottom-24 -left-24 w-96 h-96 bg-white/5 rounded-full"></div>
    <div class="absolute inset-0" style="background-image: radial-gradient(circle at 30% 50%, rgba(255,255,255,0.05) 0%, transparent 60%)"></div>
  </div>

  <div class="relative max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">

    <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-white/10 border border-white/20 rounded-full text-xs font-semibold text-white/80 mb-6">
      🚀 Get started in under 30 days
    </div>

    <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white tracking-tight mb-4">
      Ready to automate your<br class="hidden sm:block"/> finance operations?
    </h2>
    <p class="text-lg text-indigo-200 mb-10 max-w-xl mx-auto">
      See how FinOpsAI handles your specific reconciliation workflows.
      Book a 30-minute demo with our finance automation team.
    </p>

    {#if submitted}
      <div class="inline-flex flex-col items-center gap-3 bg-white/10 border border-white/20 rounded-2xl px-10 py-8">
        <div class="text-4xl">🎉</div>
        <p class="text-white font-bold text-lg">You're on the list!</p>
        <p class="text-indigo-200 text-sm">We'll reach out within 1 business day.</p>
      </div>
    {:else}
      <form onsubmit={handleSubmit} class="flex flex-col sm:flex-row gap-3 max-w-lg mx-auto mb-8">
        <label for="email-cta" class="sr-only">Work email</label>
        <input
          id="email-cta"
          type="email"
          bind:value={email}
          placeholder="your@company.com"
          required
          autocomplete="email"
          class="flex-1 px-4 py-3 rounded-xl bg-white/10 border border-white/20 text-white placeholder:text-indigo-300 focus:outline-none focus:ring-2 focus:ring-white/50 text-sm backdrop-blur-sm"
        />
        <button
          type="submit"
          class="px-6 py-3 bg-white text-indigo-700 font-bold text-sm rounded-xl hover:bg-indigo-50 transition-colors shadow-lg whitespace-nowrap"
        >
          Book a Demo →
        </button>
      </form>

      <p class="text-xs text-indigo-300">
        No spam. Unsubscribe anytime. By submitting, you agree to our
        <a href="/privacy-policy" class="underline hover:text-white">Privacy Policy</a>.
      </p>
    {/if}

    <!-- Trust row -->
    <div class="flex flex-wrap justify-center gap-6 mt-12">
      {#each ['SOC 2 Certified', 'No setup fee', 'Live in 30 days', 'Dedicated CSM'] as item}
        <div class="flex items-center gap-2 text-sm text-indigo-200">
          <svg class="w-4 h-4 text-emerald-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
          </svg>
          {item}
        </div>
      {/each}
    </div>
  </div>
</section>
