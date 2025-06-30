<script lang="ts">
  const advantages = [
    {
      title: 'Free credits',
      description: 'Empowering partners to scale.',
      icon: '💎'
    },
    {
      title: 'Special developer access',
      description: 'Get an all-access account to build unlimited PoCs for your clients.',
      icon: '👨‍💻'
    },
    {
      title: 'Knowledge sessions',
      description: 'Access to product and market sessions.',
      icon: '📖'
    },
    {
      title: 'Revenue share',
      description: 'Get monthly recurring revenues when you refer clients.',
      icon: '💵'
    },
    {
      title: 'Reduced time',
      description: 'Deliver your products much faster with our partners\' programs.',
      icon: '⏱️'
    },
    {
      title: 'On-demand support',
      description: 'Technical assistance for implementation.',
      icon: '🛟'
    },
    {
      title: 'Training and mentoring sessions',
      description: 'Enabling partners to deliver the best experience.',
      icon: '🎓'
    },
    {
      title: 'Value addition to your users',
      description: 'Enhance your offerings with seamless integrations and exclusive benefits.',
      icon: '➕'
    },
    {
      title: 'Significant passive income',
      description: 'Earn ongoing commissions with minimal effort.',
      icon: '🤑'
    }
  ];
</script>

<section class="py-20 relative overflow-hidden">
  <!-- Background decorative elements -->
  <div class="absolute inset-0 opacity-10">
    <div class="absolute top-20 left-10 w-32 h-32 bg-accent-500/20 rounded-full blur-xl"></div>
    <div class="absolute bottom-20 right-10 w-40 h-40 bg-secondary-500/20 rounded-full blur-xl"></div>
  </div>

  <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <div class="text-left mb-16">
      <p class="text-secondary-400 text-sm font-semibold uppercase tracking-wider mb-4 uppercase">Be a partner</p>
      <h2 class="text-4xl lg:text-5xl font-bold text-white mb-6">
        CometChat partner<br>
        advantages
      </h2>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each advantages as advantage}
        <div class="group p-4  backdrop-blur-sm   hover:border-accent-500/30 transition-all duration-300 hover:shadow-lg hover:shadow-accent-500/10 hover:-translate-y-1 flex flex-col items-start text-left">
          <div class="w-16 h-16 bg-gradient-to-br from-accent-500/20 to-secondary-500/20 rounded-full flex items-center justify-center text-3xl mb-6 group-hover:scale-110 transition-transform duration-300">
            {advantage.icon}
            
          </div>
          <h3 class="text-xl font-semibold text-white group-hover:text-accent-400 transition-colors">
            {advantage.title}
          </h3>
          <p class="text-gray-400 leading-relaxed">
            {advantage.description}
          </p>
        </div>
      {/each}
    </div>
  </div>
</section>