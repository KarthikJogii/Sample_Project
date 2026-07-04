<script>
  // Exact Bluecopa customers from the audit
  const logos = [
    { name: 'Mamaearth', color: '#7CB342' },
    { name: 'Navi', color: '#FF6B35' },
    { name: 'Flipkart', color: '#2874F0' },
    { name: 'Yatra', color: '#E65C00' },
    { name: 'EkaCare', color: '#00897B' },
    { name: 'Diversey', color: '#1565C0' },
    { name: 'Porter', color: '#F44336' },
    { name: 'Purplle', color: '#9C27B0' },
    { name: 'HackerEarth', color: '#2C3E50' },
    { name: 'Meesho', color: '#F43397' },
  ];

  const doubled = [...logos, ...logos];
</script>

<div class="w-full overflow-hidden relative py-8">
  <!-- Left fade -->
  <div class="absolute inset-y-0 left-0 w-20 bg-gradient-to-r from-white to-transparent z-10 pointer-events-none"></div>
  <!-- Right fade -->
  <div class="absolute inset-y-0 right-0 w-20 bg-gradient-to-l from-white to-transparent z-10 pointer-events-none"></div>

  <p class="text-xs font-medium text-[#A5A5A5] uppercase tracking-widest text-center mb-6">
    Trusted by leading enterprise finance teams
  </p>

  <div class="flex gap-6 marquee-track" style="width: max-content;">
    {#each doubled as logo}
      <div class="flex items-center gap-2.5 shrink-0 px-5 py-2.5 rounded-full border border-[#EAEAEA] bg-white hover:border-[#3548FF]/30 transition-colors">
        <!-- Color dot representing brand -->
        <div class="w-3 h-3 rounded-full shrink-0" style="background: {logo.color};"></div>
        <span class="text-sm font-semibold text-[#090909] whitespace-nowrap">{logo.name}</span>
      </div>
    {/each}
  </div>
</div>
