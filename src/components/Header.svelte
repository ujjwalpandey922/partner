<script lang="ts">
  import { hasContext, onMount } from 'svelte';
  
  let isMenuOpen = false;
  let scrolled = false;
  let activeDropdown = '';
  let activeDeveloperTab = 'Integration Methods';

  const toggleMenu = () => {
    document.body.style.overflow = isMenuOpen ? 'auto' : 'hidden';
    isMenuOpen = !isMenuOpen;
  };

  const showDropdown = (dropdown: string) => {
    activeDropdown = dropdown;
  };

  const hideDropdown = () => {
    activeDropdown = '';
  };

  const setDeveloperTab = (tab: string) => {
    activeDeveloperTab = tab;
  };

  onMount(() => {
    const handleScroll = () => {
      scrolled = window.scrollY > 20;
    };

    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });

  const menuItems = [
    { name: 'Platform', href: '#platform', hasDropdown: true },
    { name: 'Developers', href: '#developers', hasDropdown: true },
    { name: 'Solutions', href: '#solutions', hasDropdown: true },
    { name: 'Resources', href: '#resources', hasDropdown: true },
    { name: 'Customers', href: '#customers' },
    { name: 'Pricing', href: '#pricing' },
    { name: 'Demo apps', href: '#demo', isNew: true }
  ];

  // Dropdown content data
  const dropdownContent = {
    platform: {
    title: "Build with UI Kits, SDKs & APIs",
    sections: [
      {
        title: "Chat & Messaging",
        description: "Lightning-fast conversations with enterprise scalability",
        icon: `<svg width="64" height="64" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g opacity="0.2">
            <path d="M7.97718 42.4169L7.97631 42.4146C7.9286 42.2875 7.86017 42.1186 7.74757 41.8413C6.51266 38.8006 5.8335 35.4773 5.8335 32.0007C5.8335 17.5492 17.5487 5.83398 32.0002 5.83398C46.4516 5.83398 58.1669 17.5492 58.1669 32.0007C58.1669 46.4521 46.4516 58.1673 32.0002 58.1673C28.5236 58.1673 25.2002 57.4882 22.1595 56.2533C21.8823 56.1407 21.7133 56.0722 21.5863 56.0245L21.5838 56.0236L21.5469 56.01L21.4305 55.967L21.3076 55.9834L21.2949 55.9851L21.2938 55.9852C21.186 55.9998 21.043 56.0234 20.7901 56.0656L11.2259 57.6596L11.2258 57.6596C10.7918 57.7321 10.336 57.8078 9.94664 57.8372C9.52348 57.8692 8.89649 57.8757 8.24259 57.5952C7.41728 57.2412 6.75961 56.5836 6.40562 55.7582C6.12516 55.1043 6.13168 54.4774 6.16362 54.0542C6.19301 53.6649 6.26871 53.2091 6.34118 52.7752L6.3412 52.775L7.93527 43.2107C7.97741 42.9579 8.00102 42.8148 8.01563 42.707L8.01578 42.7059L8.01747 42.6932L8.03387 42.5702L7.9908 42.4537L7.97718 42.4169ZM21.3335 22.1673C19.5846 22.1673 18.1668 23.5851 18.1668 25.334C18.1668 27.0829 19.5846 28.5007 21.3335 28.5007H32.0002C33.7491 28.5007 35.1668 27.0829 35.1668 25.334C35.1668 23.5851 33.7491 22.1673 32.0002 22.1673H21.3335ZM21.3335 31.5007C19.5846 31.5007 18.1668 32.9184 18.1668 34.6673C18.1668 36.4162 19.5846 37.834 21.3335 37.834H40.0002C41.7491 37.834 43.1668 36.4162 43.1668 34.6673C43.1668 32.9184 41.7491 31.5007 40.0002 31.5007H21.3335Z" stroke="url(#paint0_linear_1386_51115)"></path>
          </g>
          <defs>
            <linearGradient id="paint0_linear_1386_51115" x1="32.0002" y1="5.33398" x2="32.0002" y2="58.6673" gradientUnits="userSpaceOnUse">
              <stop stop-color="#FAFAFF"></stop>
              <stop offset="0.285" stop-color="#B1B1B4"></stop>
              <stop offset="1" stop-color="#646465"></stop>
            </linearGradient>
          </defs>
        </svg>`,
        href: "#chat-messaging"
      },
      {
        title: "Voice & Video Calls", 
        description: "Crystal-clear calls and streams with zero lag",
        icon: `<svg width="64" height="64" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g opacity="0.2">
            <path d="M22.367 41.5601L22.3664 41.5595C18.946 38.1565 15.9482 34.4068 13.8084 30.6719C11.6653 26.9312 10.4028 23.2403 10.4028 19.9449C10.4028 17.046 11.3809 14.4434 13.5862 12.3324L13.5862 12.3324L13.5876 12.3311C14.9211 11.0449 16.4232 10.4005 17.8417 10.4005C18.9853 10.4005 19.9954 10.8364 20.726 11.8352L25.8483 19.0424C25.8485 19.0427 25.8488 19.043 25.849 19.0433C26.6165 20.1349 26.9493 20.958 26.9493 21.6586C26.9493 22.543 26.4351 23.3693 25.397 24.4531C25.3966 24.4536 25.3961 24.454 25.3956 24.4545L23.7082 26.1867C23.3394 26.5563 23.2064 26.9994 23.2064 27.4186C23.2064 27.8964 23.3962 28.32 23.5136 28.5779L23.5188 28.5892L23.5245 28.6003C23.9326 29.3897 24.6956 30.4242 25.6301 31.5366C26.571 32.6567 27.7077 33.8814 28.8841 35.0558L28.8859 35.0576C31.2437 37.3879 33.8176 39.6036 35.3681 40.4275L35.368 40.4277L35.3794 40.4334C35.6397 40.5633 36.0815 40.7478 36.5563 40.7478C36.9916 40.7478 37.4539 40.5812 37.8143 40.2221C37.8147 40.2217 37.8151 40.2213 37.8155 40.2208L39.5043 38.5586C39.5045 38.5584 39.5047 38.5582 39.5049 38.5579C40.581 37.5071 41.435 37.0109 42.3019 37.0109C43.0109 37.0109 43.8381 37.3258 44.9253 38.0642L52.2366 43.2476C52.2372 43.248 52.2378 43.2484 52.2384 43.2489C53.2093 43.9509 53.6028 44.9314 53.6028 45.9841C53.6028 47.4414 52.8911 48.9693 51.682 50.3136C49.614 52.5817 47.0581 53.6005 44.1137 53.6005C40.8139 53.6005 37.0995 52.3172 33.3306 50.1531C29.568 47.9927 25.7879 44.9755 22.367 41.5601Z" stroke="url(#paint0_linear_1324_58924)"></path>
          </g>
          <defs>
            <linearGradient id="paint0_linear_1324_58924" x1="32.0028" y1="9.90048" x2="32.0028" y2="54.1005" gradientUnits="userSpaceOnUse">
              <stop stop-color="#FAFAFF"></stop>
              <stop offset="0.285" stop-color="#B1B1B4"></stop>
              <stop offset="1" stop-color="#646465"></stop>
            </linearGradient>
          </defs>
        </svg>`,
        href: "#voice-video"
      },
      {
        title: "Chat Moderation",
        description: "AI-powered protection that catches every threat instantly",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
          <path fill="currentColor" fill-rule="evenodd" d="M3.957 9.44a4 4 0 1 1 4.226-.087l2.996 1.525 9.367-4.769a1 1 0 1 1 .908 1.782L13.384 12l8.07 4.109a1 1 0 1 1-.908 1.782l-9.367-4.769-2.996 1.526a4 4 0 1 1-3.845-.287L8.975 12 4.338 9.64a3.986 3.986 0 0 1-.38-.2ZM4 6a2 2 0 1 1 1.193 1.83l-.196-.1A2 2 0 0 1 4 6Zm.997 10.27a2 2 0 1 0 .197-.1l-.197.1Z" clip-rule="evenodd"></path>
        </svg>`,
        href: "#moderation"
      },
      {
        title: "Analytics & Insights",
        description: "Track engagement and optimize chat performance", 
        icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
          <path fill="currentColor" fill-rule="evenodd" d="M17.838 2H6.162c-.527 0-.981 0-1.356.03-.395.033-.789.104-1.167.297a3 3 0 0 0-1.311 1.311c-.193.378-.264.772-.296 1.167C2 5.18 2 5.635 2 6.161V17.84c0 .527 0 .982.03 1.356.033.395.104.789.297 1.167a3 3 0 0 0 1.311 1.311c.378.193.772.264 1.167.296.375.031.83.031 1.356.031H17.84c.527 0 .982 0 1.356-.03.395-.033.789-.104 1.167-.297a3 3 0 0 0 1.311-1.311c.193-.378.264-.772.296-1.167.031-.375.031-.83.031-1.356V6.16c0-.527 0-.981-.03-1.356-.033-.395-.104-.789-.297-1.167a3 3 0 0 0-1.311-1.311c-.378-.193-.772-.264-1.167-.296A17.9 17.9 0 0 0 17.838 2ZM17 7a1 1 0 1 0-2 0v10a1 1 0 1 0 2 0V7Zm-5 3a1 1 0 0 1 1 1v6a1 1 0 1 1-2 0v-6a1 1 0 0 1 1-1Zm-4 4a1 1 0 0 1 1 1v2a1 1 0 1 1-2 0v-2a1 1 0 0 1 1-1Z" clip-rule="evenodd"></path>
        </svg>`,
        href: "#analytics"
      },
      {
        title: "Notifications",
        description: "Perfect engagement with cross-platform alerts",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
          <path fill="currentColor" fill-rule="evenodd" d="M8.605 20.338a1 1 0 0 1 1.411-.088c.53.468 1.223.75 1.984.75a2.98 2.98 0 0 0 1.984-.75 1 1 0 1 1 1.324 1.5A4.984 4.984 0 0 1 12 23a4.985 4.985 0 0 1-3.307-1.25 1 1 0 0 1-.088-1.412ZM7.05 3.05A7 7 0 0 1 19 8c0 2.913.732 4.844 1.5 6.077l.012.02c.357.573.64 1.027.83 1.358.095.165.182.325.246.466.032.071.068.158.096.252.024.079.068.246.052.45-.012.136-.04.37-.174.611a1.48 1.48 0 0 1-.428.47c-.25.186-.538.229-.633.243h-.005a4.616 4.616 0 0 1-.483.04c-.336.013-.8.013-1.377.013H5.364c-.577 0-1.041 0-1.376-.013a4.618 4.618 0 0 1-.484-.04H3.5a1.406 1.406 0 0 1-.634-.242 1.48 1.48 0 0 1-.428-.47 1.482 1.482 0 0 1-.173-.613c-.017-.203.028-.37.05-.449.029-.094.065-.18.097-.251a5.66 5.66 0 0 1 .247-.467c.19-.33.473-.785.83-1.359l.012-.019C4.268 12.844 5 10.913 5 8a7 7 0 0 1 2.05-4.95Z" clip-rule="evenodd"></path>
        </svg>`,
        href: "#notifications"
      },
      {
        title: "Multi-Tenant Chat",
        description: "Secure isolated chat environments for multiple organizations",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
          <path fill="currentColor" fill-rule="evenodd" d="M18.032 1H5.968c-.439 0-.817 0-1.13.021a3.07 3.07 0 0 0-.986.207 3 3 0 0 0-1.624 1.624 3.07 3.07 0 0 0-.207.986C2 4.15 2 4.529 2 4.968v.064c0 .439 0 .817.021 1.13.023.33.072.66.207.986a3 3 0 0 0 1.624 1.624c.326.135.656.184.986.207C5.15 9 5.529 9 5.968 9H11v3H8.759c-.805 0-1.47 0-2.01.044-.563.046-1.08.145-1.565.392a4 4 0 0 0-1.748 1.748c-.247.485-.346 1.002-.392 1.564a19.07 19.07 0 0 0-.043 1.423 3.001 3.001 0 1 0 2 0c.002-.529.01-.93.037-1.26.035-.438.1-.663.18-.819a2 2 0 0 1 .874-.874c.156-.08.38-.145.819-.18C7.361 14 7.943 14 8.8 14H11v3.17a3.001 3.001 0 1 0 2 0V14h2.2c.857 0 1.439 0 1.889.038.438.035.663.1.819.18a2 2 0 0 1 .874.874c.08.156.145.38.18.819.027.33.035.731.037 1.26A3.001 3.001 0 0 0 20 23a3 3 0 0 0 1-5.83 19.079 19.079 0 0 0-.044-1.422c-.046-.562-.145-1.079-.392-1.564a4 4 0 0 0-1.748-1.748c-.485-.247-1.002-.346-1.564-.392C16.71 12 16.046 12 15.242 12H13V9h5.032c.439 0 .817 0 1.13-.021.33-.023.66-.072.986-.207a3 3 0 0 0 1.624-1.624c.135-.326.184-.656.207-.986C22 5.85 22 5.471 22 5.032v-.064c0-.439 0-.817-.021-1.13a3.072 3.072 0 0 0-.207-.986 3 3 0 0 0-1.624-1.624 3.07 3.07 0 0 0-.986-.207C18.85 1 18.471 1 18.032 1Z" clip-rule="evenodd"></path>
        </svg>`,
        href: "#multi-tenant"
      }
    ]
  },
    developers: {
      tabs: [
        {
          name: "Integration Methods",
          integrations: [
            { name: "React", icon: "⚛️", href: "#react-docs" },
            { name: "Angular", icon: "🅰️", href: "#angular-docs" },
            { name: "Swift", icon: "🍎", href: "#swift-docs" },
            { name: "Kotlin", icon: "📱", href: "#kotlin-docs" },
            { name: "Vue", icon: "💚", href: "#vue-docs" },
            { name: "React Native", icon: "📱", href: "#react-native-docs" },
            { name: "PHP", icon: "🐘", href: "#php-docs" },
            { name: "WordPress", icon: "📝", href: "#wordpress-docs" },
            { name: "Cordova", icon: "📱", href: "#cordova-docs" },
            { name: "Ionic", icon: "⚡", href: "#ionic-docs" },
            { name: "JavaScript", icon: "🟨", href: "#js-docs" },
            { name: "HTML5", icon: "🌐", href: "#html5-docs" }
          ],
          resources: [
            {
              title: "Sample Apps",
              description: "Reference implementations for quick starts",
              icon: "📱",
              href: "#sample-apps"
            },
            {
              title: "APIs", 
              description: "API reference for integration and management",
              icon: "🔧",
              href: "#apis"
            },
            {
              title: "Product Updates",
              description: "New features and platform updates",
              icon: "🔄",
              href: "#updates"
            },
            {
              title: "Feature Requests",
              description: "Direct input into product roadmap",
              icon: "💡",
              href: "#feature-requests"
            }
          ]
        },
        {
          name: "Developer Docs",
          subtitle: "Choose your path from no-code to full control",
          options: [
            {
              title: "UI Kits",
              description: "Component library with full styling control",
              icon: "🎨",
              href: "#ui-kits"
            },
            {
              title: "SDKs",
              description: "Native SDKs for deep integration",
              icon: "⚙️",
              href: "#sdks"
            }
          ]
        },
        {
          name: "Support",
          options: [
            {
              title: "Community",
              description: "Implementation guides and troubleshooting tips",
              icon: "👥",
              href: "#community"
            },
            {
              title: "Help Center",
              description: "Platform knowledge base and FAQs",
              icon: "❓",
              href: "#help-center"
            },
            {
              title: "Office Hours",
              description: "Live technical guidance for implementations",
              icon: "🕐",
              href: "#office-hours"
            },
            {
              title: "Report an issue",
              description: "Direct support for technical issues",
              icon: "🐛",
              href: "#report-issue"
            }
          ]
        }
      ]
    },
    solutions: {
      title: "By use case",
      useCases: [
        {
          title: "Marketplace",
          description: "Secure buyer-seller chat",
          icon: "🛒",
          href: "#marketplace"
        },
        {
          title: "Telehealth",
          description: "HIPAA-compliant healthcare communication",
          icon: "🏥",
          href: "#telehealth"
        },
        {
          title: "Dating", 
          description: "Safe conversations with AI moderation",
          icon: "💕",
          href: "#dating"
        },
        {
          title: "On-demand service",
          description: "Instant connection for service delivery",
          icon: "🚀",
          href: "#on-demand"
        },
        {
          title: "SaaS",
          description: "Enterprise chat without engineering overhead", 
          icon: "💼",
          href: "#saas"
        },
        {
          title: "Social community",
          description: "Moderated spaces for growing communities",
          icon: "👥",
          href: "#social"
        }
      ]
    },
    resources: {
      title: "Explore and learn",
      sections: [
        {
          title: "Templates",
          description: "Pre-built templates designed for various industries",
          icon: "📋",
          href: "#templates"
        },
        {
          title: "Tutorials", 
          description: "Hands-on implementation tutorials",
          icon: "🎓",
          href: "#tutorials"
        },
        {
          title: "Blog",
          description: "Industry insights and platform updates",
          icon: "📰",
          href: "#blog"
        }
      ],
      guides: [
        {
          title: "Migrate to CometChat",
          icon: "📤",
          href: "#migrate"
        },
        {
          title: "CometChat for Marketplaces",
          icon: "🛒",
          href: "#marketplace-guide"
        },
        {
          title: "CometChat for Healthcare", 
          icon: "🏥",
          href: "#healthcare-guide"
        },
        {
          title: "See All",
          icon: "👁️",
          href: "#all-guides"
        }
      ]
    }
  };


    let activeMobileView = '';
  let activeMobileDeveloperTab = dropdownContent.developers.tabs[0].name; // Default to first tab
  
  function openMobileView(name = '') {
    activeMobileView = name;
    // Reset developer tab when opening developers view
    if (name === 'developers') {
      activeMobileDeveloperTab = dropdownContent.developers.tabs[0].name;
    }
  }
  
  function closeMobileView() {
    activeMobileView = '';
  }
  
  function setMobileDeveloperTab(tabName = '') {
    activeMobileDeveloperTab = tabName;
  }
</script>

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 xl:hover:border-b-gray-200/25 xl:hover:border-b xl:hover:bg-company-700 {scrolled ? 'bg-company-700/85 backdrop-blur-md shadow-lg' : 'bg-transparent'}">
  <nav class="w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-16 w-full">
      <!-- Logo -->
      <div class="flex-shrink-0">
        <a href="/" class="text-white text-xl font-bold hover:text-accent-400 transition-colors">
          cometchat
        </a>
      </div>

      <!-- Desktop Navigation -->
      <div class="hidden xl:block">
        <div class="gap-4 flex items-center">
          {#each menuItems as item}
            <div class="relative group">
              <a 
                href={item.href} 
                class="text-gray-300 hover:text-white px-3 py-2 text-sm font-medium transition-colors relative group flex items-center gap-1"
                on:mouseenter={() => item.hasDropdown && showDropdown(item.name.toLowerCase())}
              
              >
                {item.name}
                {#if item.isNew}
                  <span class="border border-accent-500 text-accent-500 rounded text-[10px] font-semibold px-1 py-0.5">
                    New
                  </span>
                {/if}
                <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-accent-500 transition-all duration-300 group-hover:w-full"></span>
              </a>

              <!-- Dropdown Content -->
              {#if item.hasDropdown && activeDropdown === item.name.toLowerCase()}
                <div 
                  role="menu"
                  aria-orientation="vertical"
                  aria-labelledby="menu-button"
                  tabindex="0"
                  class="fixed left-[45%] transform -translate-x-1/2 top-[4rem] w-[900px] bg-company-300 rounded-xl shadow-2xl border border-gray-700/50 p-6 z-50"
                  on:mouseenter={() => showDropdown(item.name.toLowerCase())}
                  on:mouseleave={hideDropdown}
                >
                 {#if item.name === 'Platform'}
                    <div class="w-[800px]">
                      <h3 class="text-gray-400 text-sm mb-6">{dropdownContent.platform.title}</h3>
                      
                      <!-- First section: Build with UI Kits -->
                      <div class="mb-8">
                        <h4 class="text-white text-base font-medium mb-4">Build with UI Kits, SDKs & APIs</h4>
                        <div class="grid grid-cols-2 gap-4 mb-6">
                          <!-- Chat & Messaging -->
                          <a href="#chat-messaging" class="group flex items-start gap-4 p-4 rounded-lg border border-gray-700/50 hover:bg-gray-800/30 transition-colors">
                            <div class="w-16 h-16 flex items-center justify-center">
                              {@html dropdownContent.platform.sections[0].icon}
                            </div>
                            <div>
                              <h5 class="text-white font-medium mb-1 group-hover:text-purple-400 transition-colors">Chat & Messaging</h5>
                              <p class="text-gray-400 text-sm">Lightning-fast conversations with enterprise scalability</p>
                            </div>
                          </a>
                          
                          <!-- Voice & Video Calls -->
                          <a href="#voice-video" class="group flex items-start gap-4 p-4 rounded-lg border border-gray-700/50 hover:bg-gray-800/30 transition-colors">
                            <div class="w-16 h-16 flex items-center justify-center">
                              {@html dropdownContent.platform.sections[1].icon}
                            </div>
                            <div>
                              <h5 class="text-white font-medium mb-1 group-hover:text-purple-400 transition-colors">Voice & Video Calls</h5>
                              <p class="text-gray-400 text-sm">Crystal-clear calls and streams with zero lag</p>
                            </div>
                          </a>
                        </div>
                      </div>
                      
                      <!-- Second section: Manage with purpose built applications -->
                      <div>
                        <h4 class="text-white text-base font-medium mb-4">Manage with purpose built applications</h4>
                        <div class="grid grid-cols-2 gap-4">
                          <!-- Chat Moderation -->
                          <a href="#moderation" class="group flex items-center gap-3 p-3 rounded-lg hover:bg-gray-800/30 transition-colors">
                            <div class="w-10 h-10 flex items-center justify-center border border-gray-700 rounded-md group-hover:border-purple-500/50 group-hover:bg-purple-500/10 transition-colors">
                              {@html dropdownContent.platform.sections[2].icon}
                            </div>
                            <div>
                              <h5 class="text-white font-medium mb-1 group-hover:text-purple-400 transition-colors">Chat Moderation</h5>
                              <p class="text-gray-400 text-sm">AI-powered protection that catches every threat instantly</p>
                            </div>
                          </a>
                          
                          <!-- Notifications -->
                          <a href="#notifications" class="group flex items-center gap-3 p-3 rounded-lg hover:bg-gray-800/30 transition-colors">
                            <div class="w-10 h-10 flex items-center justify-center border border-gray-700 rounded-md group-hover:border-purple-500/50 group-hover:bg-purple-500/10 transition-colors">
                              {@html dropdownContent.platform.sections[4].icon}
                            </div>
                            <div>
                              <h5 class="text-white font-medium mb-1 group-hover:text-purple-400 transition-colors">Notifications</h5>
                              <p class="text-gray-400 text-sm">Perfect engagement with cross-platform alerts</p>
                            </div>
                          </a>
                          
                          <!-- Analytics & Insights -->
                          <a href="#analytics" class="group flex items-center gap-3 p-3 rounded-lg hover:bg-gray-800/30 transition-colors">
                            <div class="w-10 h-10 flex items-center justify-center border border-gray-700 rounded-md group-hover:border-purple-500/50 group-hover:bg-purple-500/10 transition-colors">
                              {@html dropdownContent.platform.sections[3].icon}
                            </div>
                            <div>
                              <h5 class="text-white font-medium mb-1 group-hover:text-purple-400 transition-colors">Analytics & Insights</h5>
                              <p class="text-gray-400 text-sm">Track engagement and optimize chat performance</p>
                            </div>
                          </a>
                          
                          <!-- Multi-Tenant Chat -->
                          <a href="#multi-tenant" class="group flex items-center gap-3 p-3 rounded-lg hover:bg-gray-800/30 transition-colors">
                            <div class="w-10 h-10 flex items-center justify-center border border-gray-700 rounded-md group-hover:border-purple-500/50 group-hover:bg-purple-500/10 transition-colors">
                              {@html dropdownContent.platform.sections[5].icon}
                            </div>
                            <div>
                              <h5 class="text-white font-medium mb-1 group-hover:text-purple-400 transition-colors">Multi-Tenant Chat</h5>
                              <p class="text-gray-400 text-sm">Secure isolated chat environments for multiple organizations</p>
                            </div>
                          </a>
                        </div>
                      </div>
                    </div> 
                  {:else if item.name === 'Developers'}
                    <div class="w-full">
                      <!-- Tab Navigation -->
                      <div class="flex border-b border-gray-700 mb-6">
                        {#each dropdownContent.developers.tabs as tab}
                          <button
                            class="px-4 py-2 text-sm font-medium transition-colors relative {activeDeveloperTab === tab.name ? 'text-blue-400' : 'text-gray-400 hover:text-white'}"
                            on:click={() => setDeveloperTab(tab.name)}
                          >
                            {tab.name}
                            {#if activeDeveloperTab === tab.name}
                              <span class="absolute bottom-0 left-0 w-full h-0.5 bg-blue-400"></span>
                            {/if}
                          </button>
                        {/each}
                      </div>

                      <!-- Tab Content -->
                      {#each dropdownContent.developers.tabs as tab}
                        {#if activeDeveloperTab === tab.name}
                          {#if tab.name === 'Integration Methods'}
                            <div class="flex gap-8">
                              <div class="flex-1">
                                <h3 class="text-blue-400 text-lg font-medium mb-4">Developer Docs</h3>
                                <h4 class="text-white text-base mb-4">Integration Methods</h4>
                                <div class="grid grid-cols-4 gap-3 mb-6">
                                  {#if tab.integrations}
                                  {#each tab.integrations as integration}
                                    <a 
                                      href={integration.href}
                                      class="flex flex-col items-center gap-2 p-2 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                                    >
                                      <span class="text-2xl">{integration.icon}</span>
                                      <span class="text-gray-300 text-xs text-center">{integration.name}</span>
                                    </a>
                                  {/each}
                                  {/if}
                                </div>
                                <div class="text-center">
                                  <a href="#docs" class="text-blue-400 hover:text-blue-300 font-medium">Go to docs</a>
                                </div>
                              </div>
                              <div class="w-px bg-gray-700"></div>
                              <div class="flex-1">
                                {#if tab.resources}
                                {#each tab.resources as resource}
                                  <a 
                                    href={resource.href}
                                    class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer mb-2"
                                  >
                                    <span class="text-xl">{resource.icon}</span>
                                    <div>
                                      <h4 class="text-white font-medium mb-1">{resource.title}</h4>
                                      <p class="text-gray-400 text-sm">{resource.description}</p>
                                    </div>
                                  </a>
                                {/each}
                                {/if}
                              </div>
                            </div>
                          {:else if tab.name === 'Developer Docs'}
                            <div class="text-center">
                              <h3 class="text-blue-400 text-lg font-medium mb-2">Developer Docs</h3>
                              <p class="text-gray-400 text-sm mb-8">{tab.subtitle}</p>
                              <div class="flex gap-8 justify-center">
                                {#if tab.options}
                                {#each tab.options as option}
                                  <a 
                                    href={option.href}
                                    class="flex flex-col items-center gap-4 p-6 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer min-w-[200px]"
                                  >
                                    <span class="text-4xl">{option.icon}</span>
                                    <div class="text-center">
                                      <h4 class="text-white font-medium mb-2">{option.title}</h4>
                                      <p class="text-gray-400 text-sm">{option.description}</p>
                                    </div>
                                  </a>
                                {/each}
                                {/if}
                              </div>
                            </div>
                          {:else if tab.name === 'Support'}
                            <div class="grid grid-cols-2 gap-4">
                              {#if tab.options}
                              {#each tab.options as option}
                                <a 
                                  href={option.href}
                                  class="flex items-start gap-3 p-4 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                                >
                                  <span class="text-2xl">{option.icon}</span>
                                  <div>
                                    <h4 class="text-white font-medium mb-1">{option.title}</h4>
                                    <p class="text-gray-400 text-sm">{option.description}</p>
                                  </div>
                                </a>
                              {/each}
                              {/if}
                            </div>
                          {/if}
                        {/if}
                      {/each}
                    </div>
                  {:else if item.name === 'Solutions'}
                    <h3 class="text-gray-400 text-sm mb-6">{dropdownContent.solutions.title}</h3>
                    <div class="grid grid-cols-2 gap-4">
                      {#each dropdownContent.solutions.useCases as useCase}
                        <a 
                          href={useCase.href}
                          class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                        >
                          <span class="text-2xl">{useCase.icon}</span>
                          <div>
                            <h4 class="text-white font-medium mb-1">{useCase.title}</h4>
                            <p class="text-gray-400 text-sm">{useCase.description}</p>
                          </div>
                        </a>
                      {/each}
                    </div>
                  {:else if item.name === 'Resources'}
                    <div class="mb-6">
                      <h3 class="text-gray-400 text-sm mb-4">{dropdownContent.resources.title}</h3>
                      <div class="flex gap-6 mb-6">
                        {#each dropdownContent.resources.sections as section}
                          <div class="flex-1 text-center">
                            <a 
                              href={section.href}
                              class="block bg-gray-800 rounded-lg p-4 hover:bg-gray-700 transition-colors cursor-pointer"
                            >
                              <span class="text-2xl mb-2 block">{section.icon}</span>
                              <h4 class="text-white font-medium mb-2">{section.title}</h4>
                              <p class="text-gray-400 text-sm">{section.description}</p>
                            </a>
                          </div>
                        {/each}
                      </div>
                    </div>
                    <div>
                      <h4 class="text-white text-base mb-4">Solution Guides</h4>
                      <div class="grid grid-cols-4 gap-3">
                        {#each dropdownContent.resources.guides as guide}
                          <a 
                            href={guide.href}
                            class="block bg-gray-800 rounded-lg p-4 hover:bg-gray-700 transition-colors cursor-pointer text-center"
                          >
                            <span class="text-2xl mb-2 block">{guide.icon}</span>
                            <h4 class="text-white font-medium text-sm">{guide.title}</h4>
                          </a>
                        {/each}
                      </div>
                    </div>
                  {/if}
                </div>
              {/if}
            </div>
          {/each}
        </div>
      </div>

      <!-- CTA Buttons -->
      <div class="hidden xl:flex items-center space-x-4">
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
      <div class="xl:hidden">
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
    <div class="xl:hidden fixed inset-0 top-12 bg-company-700 z-40 flex flex-col overflow-y-auto">
      {#if !activeMobileView}
        <!-- Initial Menu View -->
        <div class="px-6 py-8">
          <!-- Main Menu Items -->
          {#each menuItems as item}
            <div class="{item.hasDropdown ? 'border-b border-gray-800' : ''}">
              {#if item.hasDropdown}
                <!-- Dropdown trigger -->
                <button
                  role="menuitem"
                  tabindex="0"
                  aria-haspopup="true"
                  class="flex items-center justify-between w-full py-4 cursor-pointer"
                  on:click={() => openMobileView(item.name.toLowerCase())}
                >
                  <span class="text-white text-sm font-medium">
                    {item.name}
                  </span>
                  <svg 
                    class="w-5 h-5 text-gray-400" 
                    fill="none" 
                    stroke="currentColor" 
                    viewBox="0 0 24 24"
                  >
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                  </svg>
                </button>
              {:else}
                <a 
                  href={item.href}
                  class="flex items-center gap-2 py-4 text-white text-sm font-medium"
                  on:click={() => isMenuOpen = false}
                >
                  {item.name}
                  {#if item.isNew}
                      <span class="ml-2 border border-accent-500 text-accent-500 rounded text-[10px] font-semibold px-1 py-0.5">
                        New
                      </span>
                    {/if}
                </a>
              {/if}
            </div>
          {/each}
        </div>
        
        <!-- Bottom Auth Links -->
        <div class="px-6 pb-8 gap-4 flex justify-center items-center mt-auto">
          <button 
            class="w-full max-w-[200px] bg-transparent border border-gray-400/30 hover:bg-gray-700 text-white px-4 py-3 rounded-xl text-sm font-medium transition-colors"
            on:click={() => isMenuOpen = false}
          >
            Log in
          </button>
          <button 
            class="w-full max-w-[200px] bg-purple-800 hover:bg-purple-900 text-white px-4 py-3 rounded-xl text-sm font-medium transition-colors"
            on:click={() => isMenuOpen = false}
          >
            Schedule a demo
          </button>
        </div>
      
      {:else}
        <!-- Full-screen Dropdown View -->
        <div class="flex flex-col h-full">
          <!-- Back button -->
          <button 
            on:click={() => closeMobileView()}
            class="flex items-center gap-2 px-6 py-4 text-white text-sm font-medium border-b border-gray-600"
          >
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
            </svg>
            Back
          </button>
          
          <!-- Dropdown Content -->
          <div class="flex-1 overflow-y-auto px-6 py-4">
            {#if activeMobileView === 'platform'}
              <h2 class="text-white text-xl font-bold mb-6">Platform</h2>
              <h3 class="text-gray-400 text-sm mb-6">Build with UI Kits, SDKs & APIs</h3>
              
              <div class="space-y-6">
                <div class="bg-gray-800/50 rounded-lg p-4">
                  <h4 class="text-white font-medium text-lg mb-2">Chat & Messaging</h4>
                  <p class="text-gray-400 text-sm">Lightning-fast conversations with enterprise scalability</p>
                </div>
                
                <div class="bg-gray-800/50 rounded-lg p-4">
                  <h4 class="text-white font-medium text-lg mb-2">Voice & Video Calls</h4>
                  <p class="text-gray-400 text-sm">Crystal-clear calls and streams with zero lag</p>
                </div>
              </div>
              
              <h3 class="text-gray-400 text-sm mt-8 mb-4">Manage with purpose built applications</h3>
              
              <div class="space-y-4">
                <div class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors">
                  <div class="bg-blue-500/20 rounded-full p-2">
                    <svg class="w-5 h-5 text-blue-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                    </svg>
                  </div>
                  <div>
                    <h4 class="text-white font-medium">Chat Moderation</h4>
                    <p class="text-gray-400 text-sm">AI-powered protection that catches every threat instantly</p>
                  </div>
                </div>
                
                <div class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors">
                  <div class="bg-purple-500/20 rounded-full p-2">
                    <svg class="w-5 h-5 text-purple-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                    </svg>
                  </div>
                  <div>
                    <h4 class="text-white font-medium">Analytics & Insights</h4>
                    <p class="text-gray-400 text-sm">Track engagement and optimize chat performance</p>
                  </div>
                </div>
                
                <div class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors">
                  <div class="bg-green-500/20 rounded-full p-2">
                    <svg class="w-5 h-5 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                    </svg>
                  </div>
                  <div>
                    <h4 class="text-white font-medium">Notifications</h4>
                    <p class="text-gray-400 text-sm">Perfect engagement with cross-platform alerts</p>
                  </div>
                </div>
                
                <div class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors">
                  <div class="bg-yellow-500/20 rounded-full p-2">
                    <svg class="w-5 h-5 text-yellow-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" />
                    </svg>
                  </div>
                  <div>
                    <h4 class="text-white font-medium">Multi-Tenant Chat</h4>
                    <p class="text-gray-400 text-sm">Secure isolated chat environments for multiple organizations</p>
                  </div>
                </div>
              </div>
              
            {:else if activeMobileView === 'developers'}
              <h2 class="text-white text-xl font-bold mb-6">Developers</h2>
              
              <!-- Tab Navigation -->
              <div class="flex overflow-x-auto border-b border-gray-700 mb-6 pb-1">
                {#each dropdownContent.developers.tabs as tab}
                  <button
                    class="px-4 py-2 text-sm font-medium transition-colors whitespace-nowrap relative {activeMobileDeveloperTab === tab.name ? 'text-blue-400' : 'text-gray-400 hover:text-white'}"
                    on:click={() => setMobileDeveloperTab(tab.name)}
                  >
                    {tab.name}
                    {#if activeMobileDeveloperTab === tab.name}
                      <span class="absolute bottom-0 left-0 w-full h-0.5 bg-blue-400"></span>
                    {/if}
                  </button>
                {/each}
              </div>
              
              <!-- Tab Content -->
              {#each dropdownContent.developers.tabs as tab}
                {#if activeMobileDeveloperTab === tab.name}
                  {#if tab.name === 'Integration Methods'}
                    <div class="space-y-6">
                      <div>
                        <h3 class="text-blue-400 text-lg font-medium mb-4">Developer Docs</h3>
                        <h4 class="text-white text-base mb-4">Integration Methods</h4>
                        <div class="grid grid-cols-3 gap-3 mb-6">
                          {#if tab.integrations}
                          {#each tab.integrations as integration}
                            <a 
                              href={integration.href}
                              class="flex flex-col items-center gap-2 p-2 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                              on:click={() => isMenuOpen = false}
                            >
                              <span class="text-2xl">{integration.icon}</span>
                              <span class="text-gray-300 text-xs text-center">{integration.name}</span>
                            </a>
                          {/each}
                          {/if}
                        </div>
                      </div>
                      
                      <div class="border-t border-gray-700 pt-6">
                        <h4 class="text-white text-base mb-4">Resources</h4>
                        {#if tab.resources}
                        {#each tab.resources as resource}
                          <a 
                            href={resource.href}
                            class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer mb-2"
                            on:click={() => isMenuOpen = false}
                          >
                            <span class="text-xl">{resource.icon}</span>
                            <div>
                              <h4 class="text-white font-medium mb-1">{resource.title}</h4>
                              <p class="text-gray-400 text-sm">{resource.description}</p>
                            </div>
                          </a>
                        {/each}
                        {/if}
                      </div>
                    </div>
                  {:else if tab.name === 'Developer Docs'}
                    <div class="text-center">
                      <h3 class="text-blue-400 text-lg font-medium mb-2">Developer Docs</h3>
                      <p class="text-gray-400 text-sm mb-8">{tab.subtitle}</p>
                      <div class="grid grid-cols-2 gap-4">
                        {#if tab.options}
                        {#each tab.options as option}
                          <a 
                            href={option.href}
                            class="flex flex-col items-center gap-4 p-4 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                          >
                            <span class="text-3xl">{option.icon}</span>
                            <div class="text-center">
                              <h4 class="text-white font-medium mb-2">{option.title}</h4>
                              <p class="text-gray-400 text-sm">{option.description}</p>
                            </div>
                          </a>
                        {/each}
                        {/if}
                      </div>
                    </div>
                  {:else if tab.name === 'Support'}
                    <div class="grid grid-cols-1 gap-4">
                      {#if tab.options}
                      {#each tab.options as option}
                        <a 
                          href={option.href}
                          class="flex items-start gap-3 p-4 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                        >
                          <span class="text-2xl">{option.icon}</span>
                          <div>
                            <h4 class="text-white font-medium mb-1">{option.title}</h4>
                            <p class="text-gray-400 text-sm">{option.description}</p>
                          </div>
                        </a>
                      {/each}
                      {/if}
                    </div>
                  {/if}
                {/if}
              {/each}
              
            {:else if activeMobileView === 'solutions'}
              <h2 class="text-white text-xl font-bold mb-6">Solutions</h2>
              <h3 class="text-gray-400 text-sm mb-6">{dropdownContent.solutions.title}</h3>
              
              <div class="grid grid-cols-1 gap-4">
                {#each dropdownContent.solutions.useCases as useCase}
                  <a 
                    href={useCase.href}
                    class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                  >
                    <span class="text-2xl">{useCase.icon}</span>
                    <div>
                      <h4 class="text-white font-medium mb-1">{useCase.title}</h4>
                      <p class="text-gray-400 text-sm">{useCase.description}</p>
                    </div>
                  </a>
                {/each}
              </div>
              
            {:else if activeMobileView === 'resources'}
              <h2 class="text-white text-xl font-bold mb-6">Resources</h2>
              
              <div class="mb-6">
                <h3 class="text-gray-400 text-sm mb-4">{dropdownContent.resources.title}</h3>
                <div class="grid grid-cols-1 gap-4 mb-6">
                  {#each dropdownContent.resources.sections as section}
                    <a 
                      href={section.href}
                      class="flex items-start gap-3 p-3 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer"
                    >
                      <span class="text-2xl">{section.icon}</span>
                      <div>
                        <h4 class="text-white font-medium mb-1">{section.title}</h4>
                        <p class="text-gray-400 text-sm">{section.description}</p>
                      </div>
                    </a>
                  {/each}
                </div>
              </div>
              
              <div>
                <h4 class="text-white text-base mb-4">Solution Guides</h4>
                <div class="grid grid-cols-2 gap-3">
                  {#each dropdownContent.resources.guides as guide}
                    <a 
                      href={guide.href}
                      class="flex flex-col items-center gap-2 p-3 rounded-lg hover:bg-gray-800/50 transition-colors cursor-pointer text-center"
                    >
                      <span class="text-2xl">{guide.icon}</span>
                      <h4 class="text-white font-medium text-sm">{guide.title}</h4>
                    </a>
                  {/each}
                </div>
              </div>
            {/if}
          </div>
        </div>
      {/if}
    </div>
  {/if}
  </nav>
</header>
 