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
    { name: 'Community', href: '#', icon: '👥' },
    { name: 'LinkedIn', href: '#', icon: '💼' },
    { name: 'YouTube', href: '#', icon: '📺' },
    { name: 'Twitter', href: '#', icon: '🐦' },
    { name: 'GitHub', href: '#', icon: '⚡' }
  ];
</script>

<footer class="bg-dark-950 pt-16 pb-8">
  <div class="container mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Footer Links -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-8 mb-12">
      {#each footerSections as section}
        <div>
          <h3 class="text-white font-semibold mb-4 text-sm uppercase tracking-wider">
            {section.title}
          </h3>
          <ul class="space-y-3">
            {#each section.links as link}
              <li>
                <a 
                  href={link.href}
                  class="text-gray-400 hover:text-white text-sm transition-colors duration-200"
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
          <a href="/" class="text-white text-xl font-bold hover:text-accent-400 transition-colors">
            cometchat
          </a>
          <p class="text-gray-400 text-sm">
            2024 © CometChat
          </p>
        </div>

        <!-- Social Links -->
        <div class="flex items-center space-x-4">
          {#each socialLinks as social}
            <a 
              href={social.href}
              class="text-gray-400 hover:text-white transition-colors duration-200 flex items-center space-x-1 text-sm"
              aria-label={social.name}
            >
              <span class="text-base">{social.icon}</span>
              <span class="hidden sm:inline">{social.name}</span>
            </a>
          {/each}
        </div>
      </div>
    </div>
  </div>
</footer>