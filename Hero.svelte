<script>
  import LogoMarquee from './LogoMarquee.svelte';

  // Shimmer badge text split for animation
  const badgeText = 'Meet SamyxAI™ — Unified intelligence layer for enterprise finance';
</script>

<section class="relative pt-[100px] pb-0 overflow-hidden bg-white">

  <!-- Subtle grid background pattern -->
  <div
    class="absolute inset-0 pointer-events-none"
    style="background-image: radial-gradient(#EAEAEA 1px, transparent 1px); background-size: 32px 32px; opacity: 0.6;"
  ></div>

  <!-- Top gradient fade -->
  <div class="absolute inset-x-0 top-0 h-40 bg-gradient-to-b from-white to-transparent pointer-events-none z-10"></div>
  <!-- Bottom gradient fade into next section -->
  <div class="absolute inset-x-0 bottom-0 h-32 bg-gradient-to-t from-white to-transparent pointer-events-none z-10"></div>

  <div class="relative z-20 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center">

    <!-- SamyxAI badge (shimmer) -->
    <div class="inline-flex items-center gap-2 mb-6 fade-up visible" style="animation-delay: 0s;">
      <a href="/samyxai" class="inline-flex items-center gap-2.5 px-4 py-2 border border-[#EAEAEA] rounded-full bg-white hover:border-[#3548FF]/40 transition-colors shadow-sm group">
        <!-- Star icon -->
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
          <path d="M8 1l1.854 4.146L14 7l-4.146 1.854L8 13l-1.854-4.146L2 7l4.146-1.854z" fill="#3548FF"/>
        </svg>
        <span class="text-sm font-medium shimmer-badge">Meet SamyxAI™</span>
        <span class="text-sm text-[#A5A5A5] hidden sm:inline">Unified intelligence layer for enterprise finance</span>
        <svg width="14" height="14" viewBox="0 0 14 14" fill="none" class="text-[#A5A5A5]">
          <path d="M3 7h8M8 4l3 3-3 3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </a>
    </div>

    <!-- Hero headline -->
    <h1 class="text-4xl sm:text-5xl lg:text-[56px] font-bold text-[#090909] leading-[1.1] tracking-[-1.5px] mb-6 fade-up visible" style="animation-delay: 0.1s;">
      Connected finance operations<br/>
      platform for enterprise teams
    </h1>

    <!-- Sub-heading -->
    <p class="text-lg sm:text-xl text-[#A5A5A5] max-w-2xl mx-auto mb-8 leading-relaxed fade-up visible" style="animation-delay: 0.2s;">
      Bluecopa lets you unify and run your finance processes on auto-pilot,
      powered by <strong class="text-[#090909] font-semibold">SamyxAI™</strong>
    </p>

    <!-- CTA buttons -->
    <div class="flex flex-col sm:flex-row items-center justify-center gap-3 mb-16 fade-up visible" style="animation-delay: 0.3s;">
      <a
        href="/demo"
        class="px-6 py-3 text-base font-semibold text-white bg-[#3548FF] hover:bg-[#1a2bcc] rounded-lg transition-all duration-200 shadow-md hover:shadow-lg"
      >
        Book a demo
      </a>
      <a
        href="/samyxai"
        class="px-6 py-3 text-base font-medium text-[#090909] hover:text-[#3548FF] bg-transparent border border-[#EAEAEA] hover:border-[#3548FF]/40 rounded-lg transition-all duration-200"
      >
        Learn more about SamyxAI™ →
      </a>
    </div>

    <!-- Customer logo marquee embedded in hero -->
    <LogoMarquee />
  </div>
</section>
