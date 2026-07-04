<script>
  const capabilities = [
    {
      icon: '🔍',
      title: 'SamyxRecon',
      desc: 'Autonomously matches millions of transactions with learned rules, pattern recognition, and continuously improving models.',
    },
    {
      icon: '📄',
      title: 'SamyxExtract',
      desc: 'Extracts structured data from invoices, remittances, bank statements, contracts, and ERP exports—zero manual entry.',
    },
    {
      icon: '🔧',
      title: 'SamyxBuild',
      desc: 'AI-assisted rule builder suggests matching logic based on historical patterns—no SQL, no scripting required.',
    },
    {
      icon: '📝',
      title: 'SamyxNarrate',
      desc: 'Generates CFO-ready commentary, variance explanations, and board-pack narratives from your reconciliation data.',
    },
  ];

  const governance = [
    'Customer data never trains shared models',
    'Confidence thresholds before auto-posting',
    'Human approval gates for high-value actions',
    'Full AI decision audit trail',
    'Rollback and override on every action',
    'Tenant-isolated model context',
  ];
</script>

<section class="py-24 bg-gray-950 relative overflow-hidden">

  <!-- Background effects -->
  <div class="absolute inset-0 pointer-events-none">
    <div class="absolute top-0 left-1/4 w-96 h-96 bg-indigo-900/30 rounded-full blur-3xl"></div>
    <div class="absolute bottom-0 right-1/4 w-96 h-96 bg-violet-900/20 rounded-full blur-3xl"></div>
  </div>

  <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

    <!-- Header -->
    <div class="text-center mb-16">
      <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-indigo-900/50 border border-indigo-700/50 rounded-full text-xs font-semibold text-indigo-300 mb-6">
        <span class="w-1.5 h-1.5 rounded-full bg-indigo-400 animate-pulse"></span>
        AI-Native from the ground up
      </div>
      <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight mb-4">
        Meet <span class="text-indigo-400">SamyxAI</span> — your finance intelligence engine
      </h2>
      <p class="text-lg text-gray-400 max-w-2xl mx-auto">
        Foundational AI models purpose-built for finance. Not general AI bolted on—
        purpose-trained on finance workflows, with enterprise-grade governance.
      </p>
    </div>

    <!-- Capabilities grid -->
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6 mb-16">
      {#each capabilities as cap}
        <div class="bg-gray-900/60 border border-gray-800 rounded-2xl p-6 hover:border-indigo-700/50 hover:bg-gray-900 transition-all duration-200">
          <div class="text-3xl mb-4">{cap.icon}</div>
          <h3 class="font-bold text-white mb-2 font-mono tracking-tight">{cap.title}</h3>
          <p class="text-sm text-gray-400 leading-relaxed">{cap.desc}</p>
        </div>
      {/each}
    </div>

    <!-- Governance section -->
    <div class="bg-gray-900/50 border border-gray-800 rounded-2xl p-8 lg:p-12">
      <div class="grid lg:grid-cols-2 gap-10 items-center">
        <div>
          <p class="text-xs font-bold text-indigo-400 uppercase tracking-widest mb-3">AI Governance</p>
          <h3 class="text-2xl sm:text-3xl font-bold text-white mb-4">
            Autonomous finance—with controls your team trusts
          </h3>
          <p class="text-gray-400 mb-6 leading-relaxed">
            Finance AI can affect matching, reporting, approvals, and journal entries.
            Every SamyxAI action is explainable, auditable, and reversible.
          </p>
          <a href="#demo" class="inline-flex items-center gap-2 px-5 py-2.5 bg-indigo-600 hover:bg-indigo-700 text-white text-sm font-semibold rounded-xl transition-colors">
            See AI Governance details →
          </a>
        </div>
        <div class="space-y-3">
          {#each governance as item}
            <div class="flex items-start gap-3 p-3 bg-gray-800/50 rounded-xl border border-gray-700/50">
              <div class="w-5 h-5 rounded-full bg-emerald-900/50 border border-emerald-700 flex items-center justify-center shrink-0 mt-0.5">
                <svg class="w-3 h-3 text-emerald-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M5 13l4 4L19 7"/>
                </svg>
              </div>
              <span class="text-sm text-gray-300">{item}</span>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>
