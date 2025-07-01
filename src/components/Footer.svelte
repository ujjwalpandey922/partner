<script lang="ts">
  const footerSections = [
    {
      title: 'Platform',
      links: [
        { name: 'Chat & Messaging', href: '#' },
        { name: 'Voice & Video Calls', href: '#' },
        { name: 'Features', href: '#' },
        { name: 'Chat Moderation', href: '#' },
        { name: 'Notifications', href: '#' },
        { name: 'Analytics & Insights', href: '#' },
        { name: 'Multi-language Support', href: '#' },
        { name: 'Integration Methods', href: '#' },
        { name: 'UI Kits', href: '#' },
        { name: 'SDKs & APIs', href: '#' }
      ]
    },
    {
      title: 'Solutions',
      links: [
        { name: 'By use cases', href: '#' },
        { name: 'On-demand', href: '#' },
        { name: 'Online Marketplaces', href: '#' },
        { name: 'SaaS Businesses', href: '#' },
        { name: 'Virtual Events', href: '#' },
        { name: 'Healthcare & Telehealth', href: '#' },
        { name: 'Community Platforms', href: '#' },
        { name: 'Dating', href: '#' },
        { name: 'Comparison', href: '#' },
        { name: 'CometChat vs SendBird', href: '#' },
        { name: 'SendBird Alternatives', href: '#' },
        { name: 'Stream Chat Alternatives', href: '#' }
      ]
    },
    {
      title: 'Developers',
      links: [
        { name: 'Docs', href: '#' },
        { name: 'Sample Apps', href: '#' },
        { name: 'APIs', href: '#' },
        { name: 'Product Updates', href: '#' },
        { name: 'Feature Requests', href: '#' },
        { name: 'System Status', href: '#' },
        { name: 'Support', href: '#' },
        { name: 'Community', href: '#' },
        { name: 'Help Center', href: '#' },
        { name: 'Office Hours', href: '#' },
        { name: 'Report an Issue', href: '#' }
      ]
    },
    {
      title: 'Resources',
      links: [
        { name: 'Templates', href: '#' },
        { name: 'Tutorials', href: '#' },
        { name: 'Blog', href: '#' },
        { name: 'Chat UI Kit', href: '#' },
        { name: 'React Chat UI Kit', href: '#' },
        { name: 'Flutter Chat UI Kit', href: '#' },
        { name: 'Android Chat UI Kit', href: '#' },
        { name: 'React Native Chat UI Kit', href: '#' },
        { name: 'iOS Chat UI Kit', href: '#' }
      ]
    },
    {
      title: 'Company',
      links: [
        { name: 'Careers', href: '#' },
        { name: 'Partners', href: '#' },
        { name: 'Pricing', href: '#' },
        { name: 'Implementation Services', href: '#' },
        { name: 'Chat with us', href: '#' },
        { name: 'Terms and Legal', href: '#' },
        { name: 'Terms of Service', href: '#' },
        { name: 'Privacy Policy', href: '#' },
        { name: 'Sub-processors List', href: '#' },
        { name: 'Data Processing Addendum', href: '#' },
        { name: 'Vulnerability Disclosure Program', href: '#' }
      ]
    }
  ];

 const socialLinks = [
    { 
      name: 'Community', 
      href: 'https://community.cometchat.com/',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="20" height="20"><circle cx="15.5" cy="8.5" r="7.5" fill="currentColor"></circle><path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="m1 15.667 5.185-5.186M2.048 21.952l5.926-5.926M8.334 23l5.185-5.185"></path></svg>`
    },
    { 
      name: 'LinkedIn', 
      href: 'https://www.linkedin.com/company/cometchat/',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="20" height="20"><path fill="currentColor" d="M17.25 3H6.75A3.75 3.75 0 0 0 3 6.75v10.5A3.75 3.75 0 0 0 6.75 21h10.5A3.75 3.75 0 0 0 21 17.25V6.75A3.75 3.75 0 0 0 17.25 3ZM9 17.25H6.75V9H9v8.25ZM7.875 8.049a1.318 1.318 0 0 1-1.313-1.323c0-.73.588-1.323 1.313-1.323s1.313.593 1.313 1.323S8.6 8.049 7.875 8.049ZM18 17.25h-2.25v-4.203c0-2.526-3-2.335-3 0v4.203H10.5V9h2.25v1.324C13.797 8.384 18 8.24 18 12.18v5.069Z"></path></svg>`
    },
    { 
      name: 'YouTube', 
      href: 'https://www.youtube.com/c/CometChat',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="20" height="20"><path fill="currentColor" fill-rule="evenodd" d="M13.011 4.006A142.935 142.935 0 0 0 12.5 4h-1c-.024 0-.049 0-.073.003a130.477 130.477 0 0 0-2.78.05c-.885.026-1.83.065-2.656.125-.799.058-1.572.14-2.066.272l-.014.004a3.53 3.53 0 0 0-2.462 2.53A27.164 27.164 0 0 0 1 12.017c-.01 1.679.135 3.354.434 5.006a.997.997 0 0 0 .022.097 3.516 3.516 0 0 0 2.462 2.428l.006.002c.494.131 1.267.214 2.066.272.826.06 1.77.1 2.657.126A125.412 125.412 0 0 0 11.5 20h1c.024 0 .049 0 .073-.003.129 0 .276-.002.44-.004.614-.006 1.451-.02 2.34-.045.885-.027 1.83-.066 2.656-.126.799-.058 1.572-.14 2.066-.272l.014-.004a3.528 3.528 0 0 0 2.462-2.53A27.16 27.16 0 0 0 23 12.02a27.162 27.162 0 0 0-.448-5.072 3.514 3.514 0 0 0-2.497-2.54c-.486-.118-1.252-.192-2.051-.245a70.406 70.406 0 0 0-2.653-.115 138.05 138.05 0 0 0-2.339-.042ZM9.85 8.616c-.1.133-.1.372-.1.85v5.069c0 .477 0 .716.1.849a.5.5 0 0 0 .364.199c.166.012.367-.117.769-.376l3.942-2.534c.349-.224.523-.336.583-.479a.5.5 0 0 0 0-.389c-.06-.142-.234-.254-.583-.478l-3.942-2.535c-.402-.258-.603-.387-.769-.375a.5.5 0 0 0-.364.2Z" clip-rule="evenodd"></path></svg>`
    },
    { 
      name: 'X', 
      href: 'https://twitter.com/CometChat',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="20" height="20"><path fill="currentColor" d="M19.634 8.084c.012.17.012.338.012.51 0 5.204-3.963 11.207-11.208 11.207v-.003c-2.14.003-4.236-.61-6.038-1.766A7.91 7.91 0 0 0 8.23 16.4a3.944 3.944 0 0 1-3.68-2.735c.59.114 1.198.09 1.778-.068a3.94 3.94 0 0 1-3.16-3.86v-.05c.548.304 1.16.473 1.788.492a3.944 3.944 0 0 1-1.22-5.26c2 2.461 4.952 3.958 8.12 4.116a3.943 3.943 0 0 1 6.713-3.593 7.905 7.905 0 0 0 2.5-.956 3.954 3.954 0 0 1-1.731 2.178 7.834 7.834 0 0 0 2.262-.62 8.002 8.002 0 0 1-1.966 2.04Z"></path></svg>`
    },
    { 
      name: 'Github', 
      href: 'https://www.github.com/cometchat',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="20" height="20"><path fill="currentColor" fill-rule="evenodd" d="M12.008 2.4C6.695 2.4 2.4 6.727 2.4 12.08c0 4.278 2.752 7.9 6.57 9.182.477.096.652-.209.652-.465 0-.224-.016-.993-.016-1.795-2.673.577-3.23-1.154-3.23-1.154-.429-1.121-1.065-1.41-1.065-1.41-.875-.593.063-.593.063-.593.97.064 1.48.994 1.48.994.859 1.474 2.243 1.058 2.8.801.079-.625.334-1.058.604-1.298-2.132-.224-4.374-1.058-4.374-4.775A3.79 3.79 0 0 1 6.87 8.97c-.096-.24-.43-1.234.095-2.564 0 0 .812-.256 2.64.994a9.237 9.237 0 0 1 2.403-.32 9.24 9.24 0 0 1 2.402.32c1.83-1.25 2.64-.994 2.64-.994.526 1.33.191 2.324.096 2.564.62.673.986 1.539.986 2.596 0 3.718-2.243 4.536-4.39 4.776.35.305.652.881.652 1.795 0 1.298-.016 2.34-.016 2.66 0 .256.175.561.652.465a9.672 9.672 0 0 0 6.57-9.183c.016-5.352-4.295-9.679-9.592-9.679Z" clip-rule="evenodd"></path></svg>`
    }
  ];

  let activeSection: string | null = null;

  function toggleSection(title: string) {
    activeSection = activeSection === title ? null : title;
  }
</script>

<footer class="bg-company-700 pt-16 pb-8">
  <div class="container mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Mobile Accordion Footer -->
    <div class="block lg:hidden space-y-0 mb-12">
      {#each footerSections as section}
        <div class="py-3">
          <button
            on:click={() => toggleSection(section.title)}
            class="flex justify-between items-center w-full text-left text-violet-600 font-semibold text-base tracking-wider"
          >
            {section.title}
            <svg
              class={`w-5 h-5 transform transition-transform duration-200 text-violet-600 ${activeSection === section.title ? 'rotate-45' : ''}`}
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
            </svg>
          </button>
          <div class={`overflow-hidden transition-all duration-300 ${activeSection === section.title ? 'max-h-96' : 'max-h-0'}`}>
            <ul class="space-y-3 pl-0 pt-2">
              {#each section.links as link}
                <li>
                  <a 
                    href={link.href}
                    class="text-gray-200 hover:text-white font-semibold text-sm transition-colors duration-200 block py-1"
                  >
                    {link.name}
                  </a>
                </li>
              {/each}
            </ul>
          </div>
        </div>
      {/each}
    </div>

    <!-- Desktop Footer -->
    <div class="hidden lg:grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
      {#each footerSections as section}
        <div>
          <h3 class="text-violet-600 font-semibold mb-4 text-sm uppercase tracking-wider">
            {section.title}
          </h3>
          <ul class="space-y-3">
            {#each section.links as link}
              <li>
                <a 
                  href={link.href}
                  class="text-gray-200 hover:text-white font-semibold text-sm transition-colors duration-200"
                >
                  {link.name}
                </a>
              </li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>

    <!-- Bottom Section -->
    <div class="pt-8 border-t border-dark-800">
      <div class="flex flex-col lg:flex-row justify-between items-center space-y-4 lg:space-y-0">
        <!-- Logo and Copyright -->
        <div class="flex items-center space-x-6">
         
          <p class="text-gray-200 text-base font-semibold">
            2025 © CometChat
          </p>
        </div>

        <!-- Social Links -->
        <div class="flex flex-wrap gap-6 gap-y-3">
          {#each socialLinks as social}
            <a 
              href={social.href}
              class="h-5 inline-flex flex-row gap-1 rounded text-sm leading-normal tracking-widest font-semibold outline-none outline-brand-7/0 focus-visible:outline-1 focus-visible:outline-brand-7/100 text-gray-200 hover:text-white active:text-white"
              target="_blank" 
              rel="noopener noreferrer"
              aria-label={social.name}
            >
              <span class="w-5 h-5">{@html social.icon}</span>
              <span>{social.name}</span>
            </a>
          {/each}
        </div>
      </div>
    </div>
  </div>
</footer>

<style>
  /* Smooth accordion transition */
  .overflow-hidden {
    transition: max-height 0.3s ease-out;
  }
</style>