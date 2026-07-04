<script>
  import { onMount } from 'svelte';

  const models = [
    {
      name: 'Samyx Recon',
      desc: 'Automatically match transactions and flag discrepancies, at scale',
      icon: '⚡',
      color: '#3548FF',
    },
    {
      name: 'Samyx Build',
      desc: 'Automate tasks and workflows tailored to your business context',
      icon: '🔧',
      color: '#7B61FF',
    },
    {
      name: 'Samyx Narrate',
      desc: 'Ask for the root cause of variance, get key takeaways from reports, and more',
      icon: '📝',
      color: '#00B8A9',
    },
    {
      name: 'Samyx Extract',
      desc: 'From spreadsheets to PDF invoices — extract error-free structured data',
      icon: '📄',
      color: '#FF6B35',
    },
  ];

  let sectionEl;
  let visible = $state(false);
  onMount(() => {
    const obs = new IntersectionObserver(([e]) => { if (e.isIntersecting) visible = true; }, { threshold: 0.1 });
    obs.observe(sectionEl);
    return () => obs.disconnect();
  });
</script>

<section bind:this={sectionEl} class="samyx-bg py-20 sm:py-28">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

    <!-- Header -->
    <div class="text-center mb-14 {visible ? 'fade-up visible' : 'fade-up'}" style="animation-delay:0.05s">
      <!-- Star badge -->
      <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-[#3548FF]/20 border border-[#3548FF]/40 rounded-full mb-6">
        <svg width="14" height="14" viewBox="0 0 16 16" fill="none">
          <path d="M8 1l1.854 4.146L14 7l-4.146 1.854L8 13l-1.854-4.146L2 7l4.146-1.854z" fill="#3548FF"/>
        </svg>
        <span class="text-xs font-semibold text-[#3548FF] uppercase tracking-widest">SamyxAI™ Foundation Models</span>
      </div>
      <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight mb-4">
        The runtime that powers<br class="hidden sm:block"/> autonomous finance
      </h2>
      <p class="text-[#A5A5A5] max-w-xl mx-auto text-base leading-relaxed">
        Purpose-built AI models for every dimension of finance operations—reconciliation,
        workflow automation, document extraction, and intelligent narration.
      </p>
    </div>

    <!-- Model cards -->
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
      {#each models as model, i}
        <div
          class="bg-white/5 border border-white/10 rounded-2xl p-6 hover:bg-white/10 hover:border-white/20 transition-all duration-200 cursor-pointer group {visible ? 'fade-up visible' : 'fade-up'}"
          style="animation-delay: {0.1 + i * 0.08}s"
        >
          <!-- Icon -->
          <div class="w-12 h-12 rounded-xl flex items-center justify-center text-2xl mb-5"
            style="background: {model.color}20; border: 1px solid {model.color}30;">
            {model.icon}
          </div>

          <!-- Name -->
          <h3 class="text-base font-bold text-white mb-2 font-mono tracking-tight group-hover:text-[#3548FF] transition-colors">
            {model.name}
          </h3>

          <!-- Description -->
          <p class="text-sm text-[#A5A5A5] leading-relaxed">{model.desc}</p>

          <!-- Arrow link -->
          <div class="mt-5 flex items-center gap-1.5 text-xs font-semibold" style="color: {model.color}">
            Learn more
            <svg width="12" height="12" viewBox="0 0 14 14" fill="none">
              <path d="M3 7h8M8 4l3 3-3 3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
