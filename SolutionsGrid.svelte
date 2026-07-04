<script>
  import { onMount } from 'svelte';

  const solutions = [
    {
      icon: '🔗',
      title: 'Integrate your data sources',
      href: '/solutions/data-ingestion',
      desc: 'Connect every ERP, payment gateway, bank, and spreadsheet through pre-built connectors.',
    },
    {
      icon: '⚡',
      title: 'Automate your reconciliations',
      href: '/solutions/recon-automation',
      desc: 'AI-powered matching engine handles millions of transactions with 99%+ accuracy.',
    },
    {
      icon: '📅',
      title: 'Achieve continuous close',
      href: '/solutions/continuous-close',
      desc: 'Close your books continuously instead of scrambling at month-end.',
    },
    {
      icon: '🔄',
      title: 'Build automated workflows',
      href: '/solutions/automated-workflows',
      desc: 'Design approval flows, exception routing, and escalation rules with no code.',
    },
    {
      icon: '🛡️',
      title: 'Define controls and audit trails',
      href: '/solutions/controls-and-audit-trails',
      desc: 'Immutable logs, rule versioning, and SOX-ready evidence packs for every decision.',
    },
    {
      icon: '📊',
      title: 'Accelerate reporting cycles',
      href: '/solutions/accelerate-reporting-cycles',
      desc: 'AI-narrated reports, variance analysis, and KPI dashboards delivered on schedule.',
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

<section bind:this={sectionEl} class="py-20 sm:py-28 bg-white border-t border-[#EAEAEA]">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

    <div class="text-center mb-12 {visible ? 'fade-up visible' : 'fade-up'}">
      <h2 class="text-3xl sm:text-4xl font-bold text-[#090909] tracking-tight">
        Everything your finance team needs
      </h2>
    </div>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
      {#each solutions as s, i}
        <a
          href={s.href}
          class="group border border-[#EAEAEA] rounded-2xl p-6 hover:border-[#3548FF]/40 hover:shadow-md transition-all duration-200 {visible ? 'fade-up visible' : 'fade-up'}"
          style="animation-delay: {0.05 + i * 0.07}s"
        >
          <div class="text-3xl mb-4">{s.icon}</div>
          <h3 class="text-base font-bold text-[#090909] mb-2 group-hover:text-[#3548FF] transition-colors underline-offset-2 group-hover:underline">
            {s.title}
          </h3>
          <p class="text-sm text-[#A5A5A5] leading-relaxed mb-4">{s.desc}</p>
          <span class="text-xs font-semibold text-[#3548FF] inline-flex items-center gap-1">
            Know more
            <svg width="12" height="12" viewBox="0 0 14 14" fill="none">
              <path d="M3 7h8M8 4l3 3-3 3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </span>
        </a>
      {/each}
    </div>
  </div>
</section>
