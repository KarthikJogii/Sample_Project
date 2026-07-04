<script>
  const stories = [
    {
      company: 'Yatra',
      industry: 'Travel & OTA',
      icon: '✈',
      metric: '75%',
      metricLabel: 'improvement in revenue recovery',
      quote: 'We automated our entire PLB reconciliation process. What used to take 3 weeks now closes in 2 days with full audit trail.',
      name: 'VP Finance',
      bg: 'from-blue-50 to-indigo-50',
      border: 'border-blue-100',
    },
    {
      company: 'EkaCare',
      industry: 'HealthTech',
      icon: '⚕',
      metric: '85%',
      metricLabel: 'improvement in operational efficiency',
      quote: 'The AI matching engine handles 200,000+ insurance claim reconciliations monthly. Exceptions dropped from 12% to under 2%.',
      name: 'CFO',
      bg: 'from-emerald-50 to-teal-50',
      border: 'border-emerald-100',
    },
    {
      company: 'Diversey',
      industry: 'Manufacturing',
      icon: '🏭',
      metric: '99%',
      metricLabel: 'reduction in distributor reconciliation calls',
      quote: 'Distributors self-serve reconciliation through our branded portal. Zero calls, zero disputes sitting unresolved for months.',
      name: 'Finance Director',
      bg: 'from-violet-50 to-purple-50',
      border: 'border-violet-100',
    },
    {
      company: 'Porter',
      industry: 'Logistics',
      icon: '📦',
      metric: '70%',
      metricLabel: 'of reconciliation tasks fully automated',
      quote: 'Our finance team went from spending 80% of their time on reconciliation to focusing on analysis and strategy.',
      name: 'Head of Finance',
      bg: 'from-amber-50 to-orange-50',
      border: 'border-amber-100',
    },
    {
      company: 'Purplle',
      industry: 'E-commerce',
      icon: '💄',
      metric: '7x',
      metricLabel: 'faster payment reconciliation',
      quote: 'Multi-channel payment reconciliation across 8 gateways, automated. Close cycle went from 15 days to under 3.',
      name: 'Finance Controller',
      bg: 'from-pink-50 to-rose-50',
      border: 'border-pink-100',
    },
    {
      company: 'SaaS Platform',
      industry: 'HR Tech',
      icon: '💼',
      metric: '80%',
      metricLabel: 'of AR operations automated',
      quote: 'Revenue recognition, collections, and AR reconciliation are fully automated. DSO dropped by 18 days in the first quarter.',
      name: 'VP Finance',
      bg: 'from-sky-50 to-cyan-50',
      border: 'border-sky-100',
    },
  ];
</script>

<section class="py-24 bg-gray-50">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">

    <div class="text-center mb-16">
      <p class="text-xs font-bold text-indigo-600 uppercase tracking-widest mb-3">Customer Stories</p>
      <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 tracking-tight mb-4">
        Real outcomes. Real enterprises.
      </h2>
      <p class="text-lg text-gray-500 max-w-xl mx-auto">
        Finance teams across e-commerce, travel, logistics, and SaaS trust FinOpsAI for their most critical workflows.
      </p>
    </div>

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      {#each stories as story}
        <div class="bg-gradient-to-br {story.bg} border {story.border} rounded-2xl p-6 hover:shadow-md transition-shadow duration-200">
          <div class="flex items-center gap-3 mb-5">
            <div class="w-12 h-12 bg-white rounded-xl border {story.border} shadow-sm flex items-center justify-center text-2xl">
              {story.icon}
            </div>
            <div>
              <p class="font-bold text-gray-900">{story.company}</p>
              <p class="text-xs text-gray-500">{story.industry}</p>
            </div>
          </div>

          <div class="mb-5">
            <span class="text-4xl font-bold text-gray-900">{story.metric}</span>
            <p class="text-sm text-gray-600 mt-1">{story.metricLabel}</p>
          </div>

          <blockquote class="text-sm text-gray-600 italic leading-relaxed mb-4">
            "{story.quote}"
          </blockquote>

          <p class="text-xs text-gray-400 font-medium">— {story.name}, {story.company}</p>
        </div>
      {/each}
    </div>
  </div>
</section>
