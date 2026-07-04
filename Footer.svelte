<script>
  let email = $state('');
  let submitted = $state(false);
  let error = $state(false);

  function handleSubmit(e) {
    e.preventDefault();
    if (email && email.includes('@')) {
      submitted = true;
      error = false;
    } else {
      error = true;
    }
  }

  const links = {
    Platform: [
      { label: 'Order to Cash', href: '/order-to-cash' },
      { label: 'Record to Report', href: '/record-to-report' },
      { label: 'Procure to Pay', href: '/procure-to-pay' },
      { label: 'Management Reporting', href: '/management-reporting' },
      { label: 'Data Governance', href: '/data-governance-and-controls' },
    ],
    Solutions: [
      { label: 'Data Ingestion', href: '/solutions/data-ingestion' },
      { label: 'Recon Automation', href: '/solutions/recon-automation' },
      { label: 'Continuous Close', href: '/solutions/continuous-close' },
      { label: 'Automated Workflows', href: '/solutions/automated-workflows' },
      { label: 'Controls & Audit Trails', href: '/solutions/controls-and-audit-trails' },
    ],
    Resources: [
      { label: 'Resource Center', href: '/resources' },
      { label: 'Blogs', href: '/blog' },
      { label: 'Case Studies', href: '/resources/customers' },
      { label: 'E-books', href: '/ebooks' },
      { label: 'Glossary', href: '/glossary' },
    ],
    Company: [
      { label: 'About Us', href: '/about' },
      { label: 'Press Release', href: '/press' },
      { label: 'Security', href: '/security' },
      { label: 'Integrations', href: '/integrations' },
      { label: 'SamyxAI™', href: '/samyxai' },
    ],
  };
</script>

<footer class="bg-[#090909] text-white">

  <!-- Newsletter section -->
  <div class="border-b border-white/10">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <div class="grid sm:grid-cols-2 gap-8 items-center">
        <div>
          <h3 class="text-xl font-bold text-white mb-2">The future of finance starts with Bluecopa</h3>
          <p class="text-sm text-[#A5A5A5] leading-relaxed">
            Get the latest in AI-powered finance operations, insights, and product updates — straight to your inbox.
          </p>
        </div>
        <div>
          {#if submitted}
            <div class="flex items-center gap-2 text-sm text-emerald-400 font-medium">
              <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
              </svg>
              Thank you! Your submission has been received!
            </div>
          {:else}
            <form onsubmit={handleSubmit} class="flex gap-2">
              <label for="footer-email" class="sr-only">Email address</label>
              <input
                id="footer-email"
                type="email"
                bind:value={email}
                placeholder="your@company.com"
                autocomplete="email"
                required
                class="flex-1 px-4 py-2.5 bg-white/5 border {error ? 'border-red-500' : 'border-white/20'} rounded-lg text-sm text-white placeholder:text-[#A5A5A5] focus:outline-none focus:border-[#3548FF] transition-colors"
              />
              <button
                type="submit"
                class="px-4 py-2.5 bg-[#3548FF] hover:bg-[#1a2bcc] text-white text-sm font-semibold rounded-lg transition-colors whitespace-nowrap"
              >
                Subscribe
              </button>
            </form>
            {#if error}
              <p class="text-xs text-red-400 mt-1">Oops! Something went wrong while submitting the form.</p>
            {/if}
          {/if}
        </div>
      </div>
    </div>
  </div>

  <!-- Main footer links -->
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
    <div class="grid grid-cols-2 lg:grid-cols-6 gap-8">

      <!-- Brand -->
      <div class="col-span-2">
        <a href="/" class="flex items-center gap-2 mb-5" aria-label="Bluecopa home">
          <svg width="28" height="28" viewBox="0 0 32 32" fill="none">
            <rect width="32" height="32" rx="8" fill="#3548FF"/>
            <path d="M8 16c0-4.418 3.582-8 8-8s8 3.582 8 8" stroke="white" stroke-width="2.5" stroke-linecap="round"/>
            <path d="M16 10v12M11 16h10" stroke="white" stroke-width="2.5" stroke-linecap="round"/>
          </svg>
          <span class="font-bold text-white text-lg">bluecopa</span>
        </a>
        <p class="text-sm text-[#A5A5A5] leading-relaxed mb-6 max-w-xs">
          Connected finance operations platform for enterprise teams, powered by SamyxAI™.
        </p>
        <div class="flex gap-3">
          <a href="https://linkedin.com/company/bluecopa" target="_blank" rel="noreferrer"
            class="w-8 h-8 rounded-lg bg-white/5 border border-white/10 hover:bg-white/10 flex items-center justify-center transition-colors"
            aria-label="LinkedIn">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor" class="text-[#A5A5A5]">
              <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
            </svg>
          </a>
          <a href="https://twitter.com/bluecopa" target="_blank" rel="noreferrer"
            class="w-8 h-8 rounded-lg bg-white/5 border border-white/10 hover:bg-white/10 flex items-center justify-center transition-colors"
            aria-label="Twitter / X">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor" class="text-[#A5A5A5]">
              <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
            </svg>
          </a>
        </div>
      </div>

      <!-- Nav columns -->
      {#each Object.entries(links) as [section, items]}
        <div>
          <p class="text-xs font-bold text-white uppercase tracking-widest mb-4">{section}</p>
          <ul class="space-y-2.5">
            {#each items as item}
              <li>
                <a href={item.href} class="text-sm text-[#A5A5A5] hover:text-white transition-colors">
                  {item.label}
                </a>
              </li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>
  </div>

  <!-- Bottom bar -->
  <div class="border-t border-white/10">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-5 flex flex-col sm:flex-row items-center justify-between gap-3">
      <p class="text-xs text-[#A5A5A5]">Copyright © 2025 Bluecopa</p>
      <div class="flex items-center gap-5">
        <a href="/terms-of-service" class="text-xs text-[#A5A5A5] hover:text-white transition-colors">Terms of Service</a>
        <a href="/privacy" class="text-xs text-[#A5A5A5] hover:text-white transition-colors">Privacy Policy</a>
        <a href="/sitemap.xml" class="text-xs text-[#A5A5A5] hover:text-white transition-colors">Sitemap</a>
      </div>
    </div>
  </div>
</footer>
