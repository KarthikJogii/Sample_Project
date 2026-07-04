<script>
  import AnnouncementBar from './lib/AnnouncementBar.svelte';
  import Navbar from './lib/Navbar.svelte';
  import Hero from './lib/Hero.svelte';
  import SamyxAdvantage from './lib/SamyxAdvantage.svelte';
  import WaveText from './lib/WaveText.svelte';
  import FeatureSection from './lib/FeatureSection.svelte';
  import Testimonial from './lib/Testimonial.svelte';
  import SamyxAISection from './lib/SamyxAISection.svelte';
  import SecuritySection from './lib/SecuritySection.svelte';
  import IntegrationsSection from './lib/IntegrationsSection.svelte';
  import SolutionsGrid from './lib/SolutionsGrid.svelte';
  import FinalCTA from './lib/FinalCTA.svelte';
  import Footer from './lib/Footer.svelte';

  // ── Record to Report tabs ──────────────────────────────────────────
  const r2rTabs = [
    { label: 'Accelerate month-end close', heading: 'Accelerate month-end close', icon: '📅', body: 'Orchestrate every close task, dependency, and sign-off in one place. Close cycle time drops from weeks to days.' },
    { label: 'Automate transaction matching', heading: 'Automate transaction matching', icon: '⚡', body: 'AI matches millions of transactions across ERP, payments, and banks with 99%+ accuracy and configurable tolerance rules.' },
    { label: 'Automate journal entries', heading: 'Automate journal entries', icon: '📒', body: 'Auto-generate journal entries from reconciled data with full approval gates and ERP writeback—no manual posting.' },
    { label: 'Resolve exceptions on auto-pilot', heading: 'Resolve exceptions on auto-pilot', icon: '🔄', body: 'SamyxAI triages, routes, and resolves exceptions automatically. Reviewers only see what truly needs a human decision.' },
    { label: 'Stay audit-ready', heading: 'Stay audit-ready', icon: '🛡️', body: 'Immutable audit trail captures every rule change, match decision, approval, and override. Export evidence packs instantly.' },
    { label: 'Build accurate reports', heading: 'Build accurate reports', icon: '📊', body: 'AI-narrated close reports and variance explanations delivered to CFO and board on schedule, every period.' },
  ];

  // ── Order to Cash tabs ──────────────────────────────────────────────
  const o2cTabs = [
    { label: 'Boost your collection efficiency', heading: 'Boost collection efficiency', icon: '💰', body: 'Prioritize collections by risk score. Automate dunning sequences and collector assignments to reduce DSO.' },
    { label: 'Implement a smarter collections strategy', heading: 'Smarter collections strategy', icon: '🎯', body: 'Segment customers by payment behavior and apply tiered strategies—reducing write-offs and improving cash conversion.' },
    { label: 'Monitor high-risk accounts', heading: 'Monitor high-risk accounts', icon: '⚠️', body: 'Real-time alerts on accounts approaching credit limits, payment delays, or churn signals before they become losses.' },
    { label: 'Automate cash applications', heading: 'Automate cash applications', icon: '🔗', body: 'AI matches remittances to open invoices across payment gateways, banks, and customer portals with zero manual effort.' },
    { label: 'Unlock trapped revenue', heading: 'Unlock trapped revenue', icon: '🔓', body: 'Surface unapplied credits, unmatched payments, and disputed deductions that sit unresolved in your AR ledger.' },
  ];

  // ── Procure to Pay tabs ────────────────────────────────────────────
  const p2pTabs = [
    { label: 'Automate invoice ingestion', heading: 'Automate invoice ingestion', icon: '📄', body: 'Samyx Extract captures invoices from email, portal uploads, EDI, and PDFs—structured and validated automatically.' },
    { label: 'Accelerate invoice processing', heading: 'Accelerate invoice processing', icon: '⚡', body: '3-way match across PO, GRN, and invoice happens in seconds. Exceptions are routed with full context for fast resolution.' },
    { label: 'Verify vendor payments', heading: 'Verify vendor payments', icon: '✅', body: 'Payment verification against bank statements and ERP ensures zero duplicate payments and full visibility on cash out.' },
    { label: 'Minimize leakage', heading: 'Minimize leakage', icon: '🛡️', body: 'Catch duplicate invoices, incorrect rates, unapproved vendors, and tolerance breaches before payments are released.' },
    { label: 'Automate payment workflows', heading: 'Automate payment workflows', icon: '🔄', body: 'Configure approval chains, payment terms, and hold rules. Finance controllers approve with one click—full audit trail.' },
  ];

  // ── Management Reporting tabs ──────────────────────────────────────
  const mrTabs = [
    { label: 'Sales trend analysis', heading: 'Sales trend analysis', icon: '📈', body: 'AI surfaces revenue trends, cohort performance, and anomalies across segments, regions, and product lines.' },
    { label: 'Inventory tracking', heading: 'Inventory tracking', icon: '📦', body: 'Real-time inventory visibility integrated with your ERP and warehouse systems—no spreadsheet exports required.' },
    { label: 'Financial health monitoring', heading: 'Financial health monitoring', icon: '❤️', body: 'Track EBITDA, working capital, cash runway, and KPIs on a single CFO dashboard with drill-down capability.' },
  ];

  // ── Data Governance tabs ───────────────────────────────────────────
  const dgTabs = [
    { label: 'Custom workflows', heading: 'Custom workflows', icon: '🔧', body: 'Build approval, exception, and escalation workflows tailored to your finance processes—no engineering required.' },
    { label: 'Tech stack integration', heading: 'Tech stack integration', icon: '🔗', body: 'Connect your existing ERP, HRMS, CRM, and data warehouse. Rules and controls apply across every connected system.' },
    { label: 'Workflow performance', heading: 'Workflow performance', icon: '📊', body: 'Track SLA compliance, turnaround times, and bottlenecks. Optimize continuously with AI-powered recommendations.' },
  ];
</script>

<!-- Sticky top: announcement bar + navbar -->
<div class="fixed top-0 inset-x-0 z-50">
  <AnnouncementBar />
  <Navbar />
</div>

<!-- Push content below fixed header -->
<div class="pt-[calc(40px+60px)]">

  <!-- 1. Hero + logo marquee -->
  <Hero />

  <!-- 2. SamyxAI advantage stats (counter animation) -->
  <SamyxAdvantage />

  <!-- 3. Wave-text headline -->
  <WaveText />

  <!-- 4. Record to Report feature section -->
  <FeatureSection
    eyebrow="Record to Report"
    headline="Achieve continuous book closure for real-time finance visibility"
    subtext="From transaction matching to journal entries to close — every step automated and audit-ready."
    tabs={r2rTabs}
  />

  <!-- 5. Yatra testimonial -->
  <Testimonial
    stat="95%"
    statLabel="Reduction in manual efforts"
    quote="Bluecopa reconciliation automation has reduced 95% of manual efforts. With real-time cash flow visibility, we've optimized cash management for accelerated business growth."
    person="CFO"
    company="Yatra"
    industry="Travel & OTA"
    href="/customers/yatra"
  />

  <!-- 6. Order to Cash feature section -->
  <FeatureSection
    eyebrow="Order to Cash"
    headline="Make your cash flow predictable with smart AR operations"
    subtext="Collections, cash applications, and revenue recovery — all running on auto-pilot."
    tabs={o2cTabs}
  />

  <!-- 7. HRMS SaaS testimonial -->
  <Testimonial
    stat="45%"
    statLabel="Improvement in operational efficiency"
    quote="How a global HR SaaS platform automated their data stitching efforts and reduced DSO by 45%, freeing their finance team to focus on strategy instead of spreadsheets."
    person="Head of Finance"
    company="HRMS SaaS"
    industry="HR Technology"
    href="/customers"
  />

  <!-- 8. Procure to Pay feature section -->
  <FeatureSection
    eyebrow="Procure to Pay"
    headline="Maximize your cashflow with smart AP operations"
    subtext="From invoice ingestion to payment verification — zero leakage, full control."
    tabs={p2pTabs}
  />

  <!-- 9. Hackerearth / Financial services testimonial -->
  <Testimonial
    stat="60%"
    statLabel="Reduction in reconciliation errors"
    quote="How a major financial services provider improved their reconciliation accuracy by 60% and cut month-end close from days to hours with Bluecopa."
    person="VP of Finance, Tarun Mallappa"
    company="HackerEarth"
    industry="Financial Services"
    href="/customers/hackerearth"
  />

  <!-- 10. Management Reporting section -->
  <FeatureSection
    eyebrow="Management Reporting"
    headline="Make data-driven decisions by tracking key business metrics"
    subtext="AI-narrated reports, CFO dashboards, and board packs — delivered on schedule, every period."
    tabs={mrTabs}
  />

  <!-- 11. Diversey testimonial -->
  <Testimonial
    stat="80%"
    statLabel="Improvement in visibility"
    quote="How Bluecopa transformed forecasting accuracy and distributor satisfaction for Diversey — a leading hygiene products manufacturer — improving finance visibility by 80%."
    person="Rohan Mittal"
    company="Diversey"
    industry="Chemicals & Hygiene"
    href="/customers"
  />

  <!-- 12. Data Governance section -->
  <FeatureSection
    eyebrow="Data Governance & Controls"
    headline="Capture audit trails for continuous audit readiness"
    subtext="Custom workflows, immutable logs, and rule versioning — so every financial decision is traceable."
    tabs={dgTabs}
  />

  <!-- 13. SamyxAI foundation models -->
  <SamyxAISection />

  <!-- 14. Security & compliance -->
  <SecuritySection />

  <!-- 15. Integrations (dual marquee) -->
  <IntegrationsSection />

  <!-- 16. Solutions grid -->
  <SolutionsGrid />

  <!-- 17. Final CTA -->
  <FinalCTA />

  <!-- 18. Footer -->
  <Footer />
</div>
