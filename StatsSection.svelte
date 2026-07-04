<script>
  const stats = [
    { value: '2.4B+', label: 'Transactions processed monthly', icon: '⚡' },
    { value: '99.1%', label: 'Average match automation rate', icon: '🎯' },
    { value: '7x', label: 'Faster reconciliation vs manual', icon: '🚀' },
    { value: '200+', label: 'ERP, payment & data connectors', icon: '🔌' },
  ];
</script>

<section class="py-20 bg-indigo-950 relative overflow-hidden">

  <!-- Background decoration -->
  <div class="absolute inset-0 pointer-events-none opacity-20"
    style="background-image: radial-gradient(circle at 20% 50%, rgba(99,102,241,0.5) 0%, transparent 50%), radial-gradient(circle at 80% 50%, rgba(99,102,241,0.3) 0%, transparent 50%);">
  </div>

  <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-2 lg:grid-cols-4 gap-8 lg:gap-12">
      {#each stats as stat}
        <div class="text-center">
          <div class="text-3xl mb-3">{stat.icon}</div>
          <div class="text-4xl lg:text-5xl font-bold text-white mb-2 tracking-tight">{stat.value}</div>
          <p class="text-sm text-indigo-300 leading-snug">{stat.label}</p>
        </div>
      {/each}
    </div>
  </div>
</section>
