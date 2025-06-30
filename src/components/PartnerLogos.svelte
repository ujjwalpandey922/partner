<script lang="ts">
  const partners = [
    { name: 'endeavor', logo: 'endeavor' },
    { name: 'HALEON', logo: 'haleon' },
    { name: 'kahoot!', logo: 'kahoot' },
    { name: 'Konecta', logo: 'konecta' },
    { name: 'NOBROKER', logo: 'nobroker' },
    { name: 'shaadi.com', logo: 'shaadi' }
  ];
</script>

<section class="py-16 bg-company-700">
  <div class="container mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Desktop/Tablet: Static layout -->
    <div class="hidden md:flex flex-wrap items-center justify-center gap-8 lg:gap-12 opacity-70">
      {#each partners as partner}
        <div class="text-gray-400 hover:text-gray-300 transition-colors duration-300 text-xl font-medium">
          {partner.name}
        </div>
      {/each}
    </div>

    <!-- Mobile: Marquee layout -->
    <div class="md:hidden overflow-hidden">
      <div class="marquee-container">
        <div class="marquee-content">
          {#each partners as partner}
            <div class="text-gray-400 text-lg font-medium whitespace-nowrap mx-8">
              {partner.name}
            </div>
          {/each}
          <!-- Duplicate for seamless loop -->
          {#each partners as partner}
            <div class="text-gray-400 text-lg font-medium whitespace-nowrap mx-8">
              {partner.name}
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .marquee-container {
    width: 100%;
    overflow: hidden;
    position: relative;
  }

  .marquee-content {
    display: flex;
    animation: marquee 5s linear infinite;
    opacity: 0.7;
  }

  @keyframes marquee {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }

  /* Pause animation on hover */
  .marquee-container:hover .marquee-content {
    animation-play-state: paused;
  }
</style>