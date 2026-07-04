<script>
  import { onMount } from 'svelte';

  const items = [
    {
      label: 'ISO 27001',
      desc: 'We process user data in adherence with world-class information security management practices.',
      icon: '🔒',
    },
    {
      label: 'SOC 2',
      desc: 'Our security controls are independently audited for the highest level of data protection and integrity.',
      icon: '🛡️',
    },
    {
      label: 'GDPR',
      desc: 'We are fully compliant with the personal data privacy and protection safeguards mandated by the EU.',
      icon: '🇪🇺',
    },
    {
      label: 'CCPA',
      desc: 'Our platform is aligned with CCPA mandates on securely handling personal information of users.',
      icon: '⚖️',
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

    <div class="text-center mb-14 {visible ? 'fade-up visible' : 'fade-up'}">
      <p class="text-xs font-bold text-[#3548FF] uppercase tracking-widest mb-3">Security & Compliance</p>
      <h2 class="text-3xl sm:text-4xl font-bold text-[#090909] tracking-tight">
        Enterprise-grade security you can bank on
      </h2>
    </div>

    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
      {#each items as item, i}
        <div
          class="border border-[#EAEAEA] rounded-2xl p-6 hover:border-[#3548FF]/30 hover:shadow-md transition-all duration-200 {visible ? 'fade-up visible' : 'fade-up'}"
          style="animation-delay: {0.05 + i * 0.07}s"
        >
          <div class="text-3xl mb-4">{item.icon}</div>
          <h3 class="text-base font-bold text-[#090909] mb-3">{item.label}</h3>
          <p class="text-sm text-[#A5A5A5] leading-relaxed">{item.desc}</p>
        </div>
      {/each}
    </div>
  </div>
</section>
