<script>
  let visible = $state(true);
</script>

{#if visible}
<div class="announcement-bar py-2.5 px-4 text-center text-sm relative">
  <div class="max-w-7xl mx-auto flex items-center justify-center gap-3">
    <span class="text-gray-400 hidden sm:inline">🎉</span>
    <span class="text-white font-medium">
      Bluecopa raises <strong class="text-white">$7.5M</strong> from
    </span>
    <!-- Investor logos as text badges -->
    <span class="inline-flex items-center gap-2">
      <span class="px-2 py-0.5 bg-white/10 border border-white/20 rounded text-xs text-white font-semibold">Analog Capital</span>
      <span class="px-2 py-0.5 bg-white/10 border border-white/20 rounded text-xs text-white font-semibold">Blume</span>
      <span class="px-2 py-0.5 bg-white/10 border border-white/20 rounded text-xs text-white font-semibold">Dallas Venture</span>
    </span>
    <a href="/blog/bluecopa-raises-7-5m-series-a" class="text-xs text-[#3548FF] hover:underline font-medium hidden sm:inline">Read more →</a>
  </div>
  <button
    onclick={() => visible = false}
    aria-label="Dismiss"
    class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-500 hover:text-gray-300 transition-colors"
  >
    <svg width="14" height="14" viewBox="0 0 14 14" fill="none">
      <path d="M1 1l12 12M13 1L1 13" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
    </svg>
  </button>
</div>
{/if}
