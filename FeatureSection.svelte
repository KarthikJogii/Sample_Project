<script>
  /**
   * Reusable tabbed feature section.
   * Props:
   *   eyebrow   – small label above headline
   *   headline  – main section heading
   *   subtext   – paragraph under headline
   *   tabs      – array of { label, heading, body, icon }
   *   reversed  – flip layout (image left, tabs right) — not used here, tabs always left
   */
  let { eyebrow = '', headline, subtext = '', tabs } = $props();

  let activeTab = $state(0);

  import { onMount } from 'svelte';
  let sectionEl;
  let visible = $state(false);
  onMount(() => {
    const obs = new IntersectionObserver(([e]) => { if (e.isIntersecting) visible = true; }, { threshold: 0.1 });
    obs.observe(sectionEl);
    return () => obs.disconnect();
  });
</script>

<section bind:this={sectionEl} class="py-16 sm:py-24 bg-white border-t border-[#EAEAEA]">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

    <!-- Header -->
    <div class="max-w-2xl mb-12 {visible ? 'fade-up visible' : 'fade-up'}" style="animation-delay:0.05s">
      {#if eyebrow}
        <p class="text-xs font-bold text-[#3548FF] uppercase tracking-widest mb-3">{eyebrow}</p>
      {/if}
      <h2 class="text-3xl sm:text-4xl font-bold text-[#090909] leading-tight tracking-tight mb-4">{headline}</h2>
      {#if subtext}
        <p class="text-[#A5A5A5] text-base leading-relaxed">{subtext}</p>
      {/if}
    </div>

    <!-- Tabs + Content -->
    <div class="grid lg:grid-cols-5 gap-8 lg:gap-12">

      <!-- Left: tab list (2/5) -->
      <div class="lg:col-span-2 space-y-0 {visible ? 'fade-up visible' : 'fade-up'}" style="animation-delay:0.1s">
        {#each tabs as tab, i}
          <button
            onclick={() => activeTab = i}
            class="w-full text-left border-l-2 {activeTab === i ? 'border-[#3548FF]' : 'border-[#EAEAEA]'} pl-5 py-4 transition-all duration-200 group"
          >
            <div class="flex items-start gap-3">
              <span class="text-xl shrink-0 mt-0.5">{tab.icon}</span>
              <div class="flex-1">
                <p class="text-sm font-semibold {activeTab === i ? 'text-[#3548FF]' : 'text-[#090909]'} mb-1 transition-colors">
                  {tab.label}
                </p>
                <!-- Expand body on active -->
                <div class="tab-height {activeTab === i ? 'active' : ''}">
                  <p class="text-sm text-[#A5A5A5] leading-relaxed pr-4 pb-2">{tab.body}</p>
                </div>
              </div>
            </div>
          </button>
        {/each}
      </div>

      <!-- Right: feature visual (3/5) -->
      <div class="lg:col-span-3 {visible ? 'fade-up visible' : 'fade-up'}" style="animation-delay:0.2s">
        <div class="bg-[#F8F9FF] rounded-2xl border border-[#EAEAEA] overflow-hidden h-full min-h-[320px] flex flex-col">

          <!-- Mock browser chrome -->
          <div class="bg-white border-b border-[#EAEAEA] px-4 py-3 flex items-center gap-2">
            <div class="flex gap-1.5">
              <div class="w-2.5 h-2.5 rounded-full bg-[#EAEAEA]"></div>
              <div class="w-2.5 h-2.5 rounded-full bg-[#EAEAEA]"></div>
              <div class="w-2.5 h-2.5 rounded-full bg-[#EAEAEA]"></div>
            </div>
            <div class="flex-1 ml-2 bg-[#F8F9FF] rounded-md px-3 py-1 text-xs text-[#A5A5A5] border border-[#EAEAEA]">
              app.bluecopa.com
            </div>
          </div>

          <!-- Dynamic content per tab -->
          <div class="flex-1 p-6">
            <div class="mb-4">
              <span class="text-3xl">{tabs[activeTab].icon}</span>
              <h3 class="text-lg font-bold text-[#090909] mt-2">{tabs[activeTab].heading}</h3>
              <p class="text-sm text-[#A5A5A5] mt-1 leading-relaxed">{tabs[activeTab].body}</p>
            </div>

            <!-- Mock UI elements -->
            <div class="space-y-2.5 mt-6">
              {#each [90, 78, 95, 62] as pct, j}
                <div class="flex items-center gap-3">
                  <div class="text-xs text-[#A5A5A5] w-28 shrink-0">
                    {['Automation rate', 'Match accuracy', 'Exceptions resolved', 'Time saved'][j]}
                  </div>
                  <div class="flex-1 h-2 bg-[#EAEAEA] rounded-full overflow-hidden">
                    <div
                      class="h-full rounded-full transition-all duration-700"
                      style="width: {activeTab >= 0 ? pct : 0}%; background: #3548FF;"
                    ></div>
                  </div>
                  <span class="text-xs font-semibold text-[#090909] w-8 text-right">{pct}%</span>
                </div>
              {/each}
            </div>

            <!-- Status chips -->
            <div class="flex flex-wrap gap-2 mt-5">
              {#each ['Automated', 'AI-powered', 'Real-time', 'Audit-ready'] as chip}
                <span class="px-2.5 py-1 bg-[#3548FF]/8 text-[#3548FF] text-xs font-medium rounded-full border border-[#3548FF]/20">
                  ✓ {chip}
                </span>
              {/each}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
