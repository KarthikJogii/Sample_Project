<script>
  import { onMount } from 'svelte';

  // Second marquee row going opposite direction
  const row1 = ['SAP S/4HANA', 'Oracle ERP', 'NetSuite', 'Microsoft D365', 'Tally', 'Stripe', 'Razorpay', 'PayU', 'Adyen', 'Snowflake'];
  const row2 = ['BigQuery', 'Redshift', 'Salesforce', 'Chargebee', 'Zuora', 'HDFC Bank', 'ICICI Bank', 'Axis Bank', 'QuickBooks', 'Xero'];
  const doubled1 = [...row1, ...row1];
  const doubled2 = [...row2, ...row2];

  let sectionEl;
  let visible = $state(false);
  onMount(() => {
    const obs = new IntersectionObserver(([e]) => { if (e.isIntersecting) visible = true; }, { threshold: 0.1 });
    obs.observe(sectionEl);
    return () => obs.disconnect();
  });
</script>

<section bind:this={sectionEl} class="py-20 sm:py-28 bg-[#F8F9FF] border-t border-[#EAEAEA] overflow-hidden">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-12 {visible ? 'fade-up visible' : 'fade-up'}">
      <h2 class="text-3xl sm:text-4xl font-bold text-[#090909] tracking-tight mb-2">
        Works with your tech stack
      </h2>
      <div class="inline-flex items-center gap-1.5 mt-2">
        <span class="text-2xl font-bold text-[#3548FF]">200+</span>
        <span class="text-lg text-[#090909] font-medium">custom connectors</span>
      </div>
      <div class="mt-4">
        <a href="/integrations" class="text-sm font-semibold text-[#3548FF] hover:underline inline-flex items-center gap-1">
          Explore Integrations →
        </a>
      </div>
    </div>
  </div>

  <!-- Marquee row 1 (left to right) -->
  <div class="relative mb-4">
    <div class="absolute inset-y-0 left-0 w-24 bg-gradient-to-r from-[#F8F9FF] to-transparent z-10 pointer-events-none"></div>
    <div class="absolute inset-y-0 right-0 w-24 bg-gradient-to-l from-[#F8F9FF] to-transparent z-10 pointer-events-none"></div>
    <div class="flex gap-4 marquee-track" style="width: max-content;">
      {#each doubled1 as item}
        <div class="shrink-0 px-4 py-2.5 bg-white border border-[#EAEAEA] rounded-lg text-sm font-medium text-[#090909] shadow-sm whitespace-nowrap">
          {item}
        </div>
      {/each}
    </div>
  </div>

  <!-- Marquee row 2 (right to left) -->
  <div class="relative">
    <div class="absolute inset-y-0 left-0 w-24 bg-gradient-to-r from-[#F8F9FF] to-transparent z-10 pointer-events-none"></div>
    <div class="absolute inset-y-0 right-0 w-24 bg-gradient-to-l from-[#F8F9FF] to-transparent z-10 pointer-events-none"></div>
    <div
      class="flex gap-4"
      style="width: max-content; animation: marquee-scroll 45s linear infinite reverse;"
    >
      {#each doubled2 as item}
        <div class="shrink-0 px-4 py-2.5 bg-white border border-[#EAEAEA] rounded-lg text-sm font-medium text-[#090909] shadow-sm whitespace-nowrap">
          {item}
        </div>
      {/each}
    </div>
  </div>
</section>
