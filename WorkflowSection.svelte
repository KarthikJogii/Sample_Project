<script>
  const steps = [
    {
      step: '01',
      title: 'Connect your data',
      desc: 'Ingest transactions from ERP, payment gateways, billing systems, banks, and spreadsheets through 200+ pre-built connectors.',
      color: 'bg-indigo-500',
      sources: ['SAP', 'Oracle', 'NetSuite', 'Stripe', 'Razorpay', 'Snowflake'],
    },
    {
      step: '02',
      title: 'Match & reconcile',
      desc: 'AI-powered rules engine matches transactions continuously with configurable tolerance, fuzzy matching, and multi-leg support.',
      color: 'bg-violet-500',
      sources: ['Auto-match', 'Rule engine', 'Fuzzy logic', 'AI assist'],
    },
    {
      step: '03',
      title: 'Route exceptions',
      desc: 'Unmatched items are automatically categorized, prioritized, and routed to the right reviewer with full context and evidence.',
      color: 'bg-sky-500',
      sources: ['Smart routing', 'Priority queue', 'Evidence pack', 'SLA tracking'],
    },
    {
      step: '04',
      title: 'Approve & close',
      desc: 'Finance controllers approve, override, or escalate with a full audit trail. Post journal entries and generate close reports automatically.',
      color: 'bg-emerald-500',
      sources: ['4-eye approval', 'JE writeback', 'Audit trail', 'Close report'],
    },
  ];

  const platforms = [
    {
      title: 'Reconciliation Engine',
      desc: 'High-throughput matching for millions of transactions daily. Handles multi-source, multi-currency, and multi-leg reconciliation out of the box.',
      icon: '⚙️',
      features: ['Multi-source matching', 'Tolerance rules', 'Fuzzy matching', 'AI auto-match'],
    },
    {
      title: 'Finance Data Hub',
      desc: 'Your single source of truth. Connect, normalize, and govern finance data from every source system without ETL complexity.',
      icon: '🗄️',
      features: ['200+ connectors', 'Data normalization', 'Real-time sync', 'Schema mapping'],
    },
    {
      title: 'Close Management',
      desc: 'Orchestrate the full financial close with task lists, approvals, dependencies, and real-time visibility across teams.',
      icon: '📅',
      features: ['Close calendar', 'Task workflows', 'Sign-off control', 'Stakeholder view'],
    },
    {
      title: 'AI Agents',
      desc: 'SamyxAI agents autonomously handle matching, exception triage, document extraction, and narrative generation—with human-in-the-loop controls.',
      icon: '🤖',
      features: ['Auto-triage', 'Document extract', 'Narrative AI', 'Policy gates'],
    },
    {
      title: 'Governance & Controls',
      desc: 'RBAC, approval workflows, SOX-ready evidence management, immutable audit logs, and rule versioning for every financial decision.',
      icon: '🛡️',
      features: ['RBAC', 'Immutable logs', 'Rule versioning', 'Evidence packs'],
    },
    {
      title: 'Management Reporting',
      desc: 'AI-narrated reports delivered to CFO and board on schedule. Variance analysis, KPI dashboards, and Excel/PowerPoint export ready.',
      icon: '📊',
      features: ['AI narratives', 'Variance analysis', 'CFO dashboards', 'Auto-export'],
    },
  ];
</script>

<!-- Workflow steps -->
<section id="workflow" class="py-24 bg-white">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

    <div class="text-center mb-16">
      <p class="text-xs font-bold text-indigo-600 uppercase tracking-widest mb-3">How It Works</p>
      <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 tracking-tight mb-4">
        From raw data to close—<span class="text-indigo-600">automated</span>
      </h2>
      <p class="text-lg text-gray-500 max-w-2xl mx-auto">
        A complete workflow: ingest, match, route, approve, and close. No spreadsheet handoffs, no manual chasing.
      </p>
    </div>

    <!-- Steps -->
    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-20">
      {#each steps as step, i}
        <div class="relative">
          {#if i < steps.length - 1}
            <div class="hidden lg:block absolute top-10 left-full w-full h-px border-t-2 border-dashed border-gray-200 z-0" style="width: calc(100% - 2rem); left: calc(100% - 1rem)"></div>
          {/if}
          <div class="relative bg-white border border-gray-100 rounded-2xl p-6 shadow-sm hover:shadow-md hover:border-indigo-100 transition-all duration-200">
            <div class="flex items-center gap-3 mb-4">
              <div class="{step.color} w-10 h-10 rounded-xl flex items-center justify-center text-white font-bold text-sm shrink-0">
                {step.step}
              </div>
              <h3 class="font-semibold text-gray-900">{step.title}</h3>
            </div>
            <p class="text-sm text-gray-500 mb-4 leading-relaxed">{step.desc}</p>
            <div class="flex flex-wrap gap-1.5">
              {#each step.sources as tag}
                <span class="text-xs px-2 py-0.5 bg-gray-50 border border-gray-200 text-gray-600 rounded-full">{tag}</span>
              {/each}
            </div>
          </div>
        </div>
      {/each}
    </div>

    <!-- Platform modules -->
    <div class="text-center mb-12">
      <p class="text-xs font-bold text-indigo-600 uppercase tracking-widest mb-3">The Platform</p>
      <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 tracking-tight">
        One platform. Every finance workflow.
      </h2>
    </div>

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      {#each platforms as module}
        <div class="group bg-white border border-gray-100 rounded-2xl p-6 hover:shadow-lg hover:border-indigo-100 transition-all duration-200 cursor-pointer">
          <div class="text-3xl mb-4">{module.icon}</div>
          <h3 class="text-lg font-bold text-gray-900 mb-2 group-hover:text-indigo-700 transition-colors">{module.title}</h3>
          <p class="text-sm text-gray-500 mb-4 leading-relaxed">{module.desc}</p>
          <ul class="space-y-1.5">
            {#each module.features as feat}
              <li class="flex items-center gap-2 text-sm text-gray-600">
                <svg class="w-4 h-4 text-emerald-500 shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                </svg>
                {feat}
              </li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>
  </div>
</section>
