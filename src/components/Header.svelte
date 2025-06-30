<script lang="ts">
  import { onMount } from 'svelte';
  
  let isMenuOpen = false;
  let scrolled = false;

  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
  };

  onMount(() => {
    const handleScroll = () => {
      scrolled = window.scrollY > 20;
    };

    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });

  const menuItems = [
    { name: 'Platform', href: '#platform' },
    { name: 'Developers', href: '#developers' },
    { name: 'Solutions', href: '#solutions' },
    { name: 'Resources', href: '#resources' },
    { name: 'Customers', href: '#customers' },
    { name: 'Pricing', href: '#pricing' },
    { name: 'Demo apps', href: '#demo', isNew: true }
  ];
</script>

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 {scrolled ? 'bg-dark-900/95 backdrop-blur-md shadow-lg' : 'bg-transparent'}">
  <nav class="w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-16 w-full">
      <!-- Logo -->
      <div class="flex-shrink-0">
        <a href="/" class="text-white text-xl font-bold hover:text-accent-400 transition-colors">
          cometchat
        </a>
      </div>

      <!-- Desktop Navigation -->
      <div class="hidden md:block">
        <div class="ml-10 flex items-center space-x-8">
          {#each menuItems as item}
            <a 
              href={item.href} 
              class="text-gray-300 hover:text-white px-3 py-2 text-sm font-medium transition-colors relative group "
            >
              {item.name}
              {#if item.isNew}
                <span class="border border-accent-500 text-accent-500 rounded text-[10px] font-semibold px-1  py-0.5">
                  New
                </span>
              {/if}
              <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-accent-500 transition-all duration-300 group-hover:w-full"></span>
            </a>
          {/each}
        </div>
      </div>

      <!-- CTA Buttons -->
      <div class="hidden md:flex items-center space-x-4">
        <a 
          href="#login" 
          class="text-gray-300 hover:text-white px-4 py-2 text-sm font-medium transition-colors"
        >
          Log in
        </a>
        <a 
          href="#schedule-demo" 
          class="bg-accent-600 hover:bg-accent-700 text-white px-4 py-2 rounded-lg text-sm font-medium transition-all duration-300 hover:shadow-lg hover:shadow-accent-500/25"
        >
          Schedule a demo
        </a>
      </div>

      <!-- Mobile menu button -->
      <div class="md:hidden">
        <button
          on:click={toggleMenu}
          class="text-gray-300 hover:text-white p-2 rounded-md transition-colors"
          aria-label="Toggle menu"
        >
          <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            {#if isMenuOpen}
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            {:else}
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            {/if}
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Navigation -->
    {#if isMenuOpen}
      <div class="md:hidden bg-dark-800/95 backdrop-blur-md rounded-lg mt-2 p-4">
        <div class="space-y-3">
          {#each menuItems as item}
            <a 
              href={item.href} 
              class="text-gray-300 hover:text-white px-3 py-2 text-base font-medium transition-colors relative "
              on:click={() => isMenuOpen = false}
            >
              {item.name}
              {#if item.isNew}
                <span class="border border-accent-50 bg-transparent text-accent-50 px-1 py-0.5 rounded text-[10px] font-semibold">
                  New
                </span>
              {/if}
            </a>
          {/each}
          <div class="pt-4 mt-4 border-t border-gray-700 space-y-3">
            <a 
              href="#login" 
              class="block text-gray-300 hover:text-white px-3 py-2 text-base font-medium transition-colors"
              on:click={() => isMenuOpen = false}
            >
              Log in
            </a>
            <a 
              href="#schedule-demo" 
              class="block bg-accent-600 hover:bg-accent-700 text-white px-3 py-2 rounded-lg text-base font-medium transition-colors text-center"
              on:click={() => isMenuOpen = false}
            >
              Schedule a demo
            </a>
          </div>
        </div>
      </div>
    {/if}
  </nav>
</header>