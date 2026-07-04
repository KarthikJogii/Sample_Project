<script>
  let mobileOpen = $state(false);
  let openMenu = $state(null);

  const nav = [
    {
      label: 'Platform',
      items: [
        'Order to Cash', 'Record to Report', 'Procure to Pay',
        'Data Governance and Controls', 'Management Reporting',
        'Integrations', 'Security', 'SamyxAI',
      ],
    },
    {
      label: 'Solutions',
      items: [
        'Data Ingestion', 'Recon Automation', 'Continuous Close',
        'Automated Workflows', 'Controls and Audit Trails', 'Accelerate Reporting Cycles',
      ],
    },
    {
      label: 'Resources',
      items: ['Resource Center', 'Blogs', 'Case Studies', 'E-books', 'Glossary'],
    },
    {
      label: 'Company',
      items: ['About Us', 'Press Release'],
    },
  ];

  function slug(s) { return s.toLowerCase().replace(/\s+/g, '-'); }
</script>

<nav class="fixed top-0 inset-x-0 z-50 bg-white border-b border-[#EAEAEA]">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-[60px]">

      <!-- Bluecopa Logo -->
      <a href="/" class="flex items-center gap-2 shrink-0" aria-label="Bluecopa home">
        <svg width="32" height="32" viewBox="0 0 32 32" fill="none">
          <rect width="32" height="32" rx="8" fill="#3548FF"/>
          <path d="M8 16c0-4.418 3.582-8 8-8s8 3.582 8 8" stroke="white" stroke-width="2.5" stroke-linecap="round"/>
          <path d="M16 10v12M11 16h10" stroke="white" stroke-width="2.5" stroke-linecap="round"/>
        </svg>
        <span class="font-bold text-[#090909] text-xl tracking-tight">bluecopa</span>
      </a>

      <!-- Desktop nav -->
      <div class="hidden lg:flex items-center">
        {#each nav as item}
          <div class="relative">
            <button
              onclick={() => openMenu = openMenu === item.label ? null : item.label}
              class="flex items-center gap-1 px-4 py-5 text-sm font-medium text-[#090909] hover:text-[#3548FF] transition-colors"
            >
              {item.label}
              <svg
                class="w-3.5 h-3.5 text-[#A5A5A5] transition-transform duration-300 {openMenu === item.label ? 'rotate-180' : ''}"
                fill="none" viewBox="0 0 24 24" stroke="currentColor"
              >
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
              </svg>
            </button>

            {#if openMenu === item.label}
              <div class="absolute top-full left-0 w-60 bg-white border border-[#EAEAEA] shadow-lg rounded-xl py-2 z-50">
                {#each item.items as child}
                  <a
                    href="/{slug(child)}"
                    class="block px-4 py-2.5 text-sm text-[#090909] hover:text-[#3548FF] hover:bg-[#f5f6ff] transition-colors"
                  >{child}</a>
                {/each}
              </div>
            {/if}
          </div>
        {/each}
      </div>

      <!-- Book a demo -->
      <div class="hidden lg:block">
        <a
          href="/demo"
          class="px-5 py-2.5 text-sm font-semibold text-white bg-[#3548FF] hover:bg-[#1a2bcc] rounded-lg transition-colors"
        >
          Book a demo
        </a>
      </div>

      <!-- Mobile burger -->
      <button
        onclick={() => mobileOpen = !mobileOpen}
        class="lg:hidden p-2 rounded-md text-[#090909]"
        aria-label="Toggle menu"
      >
        <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          {#if mobileOpen}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          {:else}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          {/if}
        </svg>
      </button>
    </div>
  </div>

  <!-- Mobile menu -->
  {#if mobileOpen}
    <div class="lg:hidden border-t border-[#EAEAEA] bg-white">
      <div class="px-4 py-4 space-y-1 max-h-[80vh] overflow-y-auto">
        {#each nav as item}
          <div class="mb-3">
            <p class="text-xs font-bold text-[#A5A5A5] uppercase tracking-widest py-1">{item.label}</p>
            {#each item.items as child}
              <a href="/{slug(child)}" class="block py-2 text-sm text-[#090909] hover:text-[#3548FF]">{child}</a>
            {/each}
          </div>
        {/each}
        <div class="pt-4 border-t border-[#EAEAEA]">
          <a href="/demo" class="block w-full text-center py-3 text-sm font-semibold text-white bg-[#3548FF] rounded-lg">
            Book a demo
          </a>
        </div>
      </div>
    </div>
  {/if}
</nav>

<!-- Dismiss dropdown on outside click -->
{#if openMenu}
  <button
    onclick={() => openMenu = null}
    class="fixed inset-0 z-40 cursor-default"
    aria-hidden="true"
    tabindex="-1"
  ></button>
{/if}
