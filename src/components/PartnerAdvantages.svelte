<script lang="ts">
  const advantages = [
    {
      title: 'Free credits',
      description: 'Empowering partners to scale.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" d="M5.863 1H6a1 1 0 1 1 0 2c-.994 0-1.295.009-1.518.068a2 2 0 0 0-1.414 1.414C3.008 4.705 3 5.006 3 6a1 1 0 0 1-2 0v-.137c0-.796 0-1.387.136-1.898a4 4 0 0 1 2.829-2.829C4.476 1 5.067 1 5.863 1Zm13.655 2.068C19.295 3.008 18.994 3 18 3a1 1 0 1 1 0-2h.138c.795 0 1.386 0 1.897.136a4 4 0 0 1 2.829 2.829C23 4.476 23 5.067 23 5.863V6a1 1 0 1 1-2 0c0-.994-.009-1.295-.068-1.518a2 2 0 0 0-1.414-1.414ZM9 2a1 1 0 0 1 1-1h4a1 1 0 1 1 0 2h-4a1 1 0 0 1-1-1ZM2 9a1 1 0 0 1 1 1v1.536c.06-.035.122-.068.184-.1.485-.247 1.002-.346 1.564-.392C5.29 11 5.954 11 6.758 11h.483c.805 0 1.47 0 2.01.044.563.046 1.08.145 1.565.392a4 4 0 0 1 1.748 1.748c.247.485.346 1.002.392 1.564.044.541.044 1.206.044 2.01v.483c0 .805 0 1.47-.044 2.01-.046.563-.145 1.08-.392 1.565a3.935 3.935 0 0 1-.1.184H14a1 1 0 1 1 0 2H6.76c-.805 0-1.47 0-2.01-.044-.563-.046-1.08-.145-1.565-.392a4 4 0 0 1-1.748-1.748c-.247-.485-.346-1.002-.392-1.564C1 18.71 1 18.046 1 17.242V10a1 1 0 0 1 1-1Zm20 0a1 1 0 0 1 1 1v4a1 1 0 1 1-2 0v-4a1 1 0 0 1 1-1Zm0 8a1 1 0 0 1 1 1v.138c0 .795 0 1.386-.136 1.897a4 4 0 0 1-2.829 2.829c-.511.137-1.102.137-1.897.136H18a1 1 0 1 1 0-2c.994 0 1.296-.009 1.518-.068a2 2 0 0 0 1.414-1.414c.06-.223.068-.524.068-1.518a1 1 0 0 1 1-1Z"></path>
      </svg>`
    },
    {
      title: 'Revenue share',
      description: 'Get monthly recurring revenues when you refer clients.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" d="M7.203 7.203a8 8 0 1 0 3.595 15.595A8 8 0 0 0 7.202 7.202Z"></path>
        <path fill="currentColor" d="M8.044 5.045A10.1 10.1 0 0 1 9 5c5.523 0 10 4.477 10 10 0 .322-.015.641-.045.956a8 8 0 1 0-10.91-10.91Z"></path>
      </svg>`
    },
    {
      title: 'Training and mentoring sessions',
      description: 'Enabling partners to deliver the best experience.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" d="M12 1a1 1 0 0 1 1 1v1h5.838c.528 0 .982 0 1.357.03.395.033.789.104 1.167.297a3 3 0 0 1 1.311 1.311c.193.378.264.772.296 1.167.031.375.031.83.031 1.356v6.678c0 .527 0 .981-.03 1.356-.033.395-.104.789-.297 1.167a3 3 0 0 1-1.311 1.311c-.378.193-.772.264-1.167.296-.375.031-.83.031-1.356.031h-1.425l3.293 3.293a1 1 0 0 1-1.414 1.414L14.586 18H13v4a1 1 0 1 1-2 0v-4H9.414l-4.707 4.707a1 1 0 0 1-1.414-1.414L6.586 18H5.16c-.527 0-.981 0-1.356-.03-.395-.033-.789-.104-1.167-.297a3 3 0 0 1-1.311-1.311c-.193-.378-.264-.772-.296-1.167C1 14.82 1 14.365 1 13.839V7.16c0-.527 0-.981.03-1.356.033-.395.104-.789.297-1.167a3 3 0 0 1 1.311-1.311c.378-.193.772-.264 1.167-.296C4.18 3 4.635 3 5.161 3H11V2a1 1 0 0 1 1-1Z"></path>
      </svg>`
    },
    {
      title: 'Special developer access',
      description: 'Get an all-access account to build unlimited PoCs for your clients.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" fill-rule="evenodd" d="M17.838 2H6.162c-.527 0-.981 0-1.356.03-.395.033-.789.104-1.167.297a3 3 0 0 0-1.311 1.311c-.193.378-.264.772-.296 1.167C2 5.18 2 5.635 2 6.161V17.84c0 .527 0 .982.03 1.356.033.395.104.789.297 1.167a3 3 0 0 0 1.311 1.311c.378.193.772.264 1.167.296.375.031.83.031 1.356.031H17.84c.527 0 .982 0 1.356-.03.395-.033.789-.104 1.167-.297a3 3 0 0 0 1.311-1.311c.193-.378.264-.772.296-1.167.031-.375.031-.83.031-1.356V6.16c0-.527 0-.981-.03-1.356-.033-.395-.104-.789-.297-1.167a3 3 0 0 0-1.311-1.311c-.378-.193-.772-.264-1.167-.296A17.9 17.9 0 0 0 17.838 2Zm-7.13 5.707a1 1 0 0 0-1.415-1.414l-3 3a1 1 0 0 0 0 1.414l3 3a1 1 0 0 0 1.414-1.414L8.414 10l2.293-2.293Zm4 2.586a1 1 0 1 0-1.415 1.414L15.586 14l-2.293 2.293a1 1 0 0 0 1.414 1.414l3-3a1 1 0 0 0 0-1.414l-3-3Z" clip-rule="evenodd"></path>
      </svg>`
    },
    {
      title: 'Reduced time',
      description: 'Deliver your products much faster with our partners\' programs.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" fill-rule="evenodd" d="M1 12C1 5.925 5.925 1 12 1s11 4.925 11 11-4.925 11-11 11S1 18.075 1 12Zm12-6a1 1 0 1 0-2 0v6a1 1 0 0 0 .553.894l4 2a1 1 0 1 0 .894-1.788L13 11.382V6Z" clip-rule="evenodd"></path>
      </svg>`
    },
    {
      title: 'Value addition to your users',
      description: 'Enhance your offerings with seamless integrations and exclusive benefits.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" fill-rule="evenodd" d="M17.838 2H6.162c-.527 0-.981 0-1.356.03-.395.033-.789.104-1.167.297a3 3 0 0 0-1.311 1.311c-.193.378-.264.772-.296 1.167C2 5.18 2 5.635 2 6.161V17.84c0 .527 0 .982.03 1.356.033.395.104.789.297 1.167a3 3 0 0 0 1.311 1.311c.378.193.772.264 1.167.296.375.031.83.031 1.356.031H17.84c.527 0 .982 0 1.356-.03.395-.033.789-.104 1.167-.297a3 3 0 0 0 1.311-1.311c.193-.378.264-.772.296-1.167.031-.375.031-.83.031-1.356V6.16c0-.527 0-.981-.03-1.356-.033-.395-.104-.789-.297-1.167a3 3 0 0 0-1.311-1.311c-.378-.193-.772-.264-1.167-.296A17.9 17.9 0 0 0 17.838 2ZM17 7a1 1 0 1 0-2 0v10a1 1 0 1 0 2 0V7Zm-5 3a1 1 0 0 1 1 1v6a1 1 0 1 1-2 0v-6a1 1 0 0 1 1-1Zm-4 4a1 1 0 0 1 1 1v2a1 1 0 1 1-2 0v-2a1 1 0 0 1 1-1Z" clip-rule="evenodd"></path>
      </svg>`
    },
    {
      title: 'Knowledge sessions',
      description: 'Access to product and market sessions.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" fill-rule="evenodd" d="M3.044 19.252c.046.562.145 1.079.392 1.564a4 4 0 0 0 1.748 1.748c.485.247 1.002.346 1.564.392.541.044 1.206.044 2.01.044h8.08c.527 0 .982 0 1.357-.03.395-.033.788-.104 1.167-.297a3 3 0 0 0 1.31-1.311c.194-.378.265-.772.297-1.167.028-.336.03-.736.03-1.195V5.161c0-.527 0-.981-.03-1.356-.032-.395-.103-.789-.296-1.167a3 3 0 0 0-1.311-1.311c-.379-.193-.772-.264-1.167-.296C17.82 1 17.365 1 16.838 1h-8.08c-.804 0-1.469 0-2.01.044-.562.046-1.079.145-1.564.392a4 4 0 0 0-1.748 1.748c-.247.485-.346 1.002-.392 1.564C3 5.29 3 5.954 3 6.758v10.483c0 .671-.01 1.343.044 2.01Zm15.932.78c-.022.272-.06.372-.085.422a1 1 0 0 1-.437.437c-.05.025-.15.063-.422.085-.283.023-.656.024-1.232.024h-8c-.857 0-1.44 0-1.89-.038-.438-.035-.662-.1-.818-.18a2 2 0 0 1-.874-.874c-.18-.352-.268-.656-.201-1.168A2 2 0 0 1 7 17h12c0 1.005.058 2.03-.024 3.032Z" clip-rule="evenodd"></path>
      </svg>`
    },
    {
      title: 'On-demand support',
      description: 'Technical assistance for implementation.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" fill-rule="evenodd" d="M12 1C5.925 1 1 5.925 1 12s4.925 11 11 11 11-4.925 11-11S18.075 1 12 1Zm-1.093 7.271a2 2 0 0 1 3.013 1.727V10c0 .47-.365.958-1.055 1.418a6.05 6.05 0 0 1-1.262.634 1 1 0 0 0 .633 1.897l.169-.061a8.05 8.05 0 0 0 1.57-.806c.81-.54 1.944-1.55 1.945-3.081a4 4 0 0 0-7.773-1.333 1 1 0 0 0 1.886.664 2 2 0 0 1 .874-1.06ZM12 16a1 1 0 1 0 0 2h.01a1 1 0 0 0 0-2H12Z" clip-rule="evenodd"></path>
      </svg>`
    },
    {
      title: 'Significant passive income',
      description: 'Earn ongoing commissions with minimal effort.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" width="16" height="16">
        <path fill="currentColor" d="M16.5 2a4.5 4.5 0 1 0 0 9 4.5 4.5 0 0 0 0-9Zm-4.468-.22A6.482 6.482 0 0 0 10 6.5a6.47 6.47 0 0 0 .888 3.282 4.5 4.5 0 1 1 1.144-8.003Zm5.677 14.113c0 .792-.523 1.46-1.245 1.684l.464-.021c.507 0 1-.16 1.405-.456l2.829-2.063a1.811 1.811 0 0 1 2.318.16 1.691 1.691 0 0 1 0 2.44l-2.427 2.361a4.73 4.73 0 0 1-2.393 1.246l-3.431.668a4.809 4.809 0 0 1-2.055-.048l-3.103-.754a4.757 4.757 0 0 0-1.134-.137c-.407 0-.61 0-.773-.058a1 1 0 0 1-.606-.606c-.058-.163-.058-.366-.058-.773v-3.429c0-.285 0-.428.037-.56a1 1 0 0 1 .157-.324c.081-.11.194-.199.419-.375l1.185-.93S11.263 13 12.348 13c.45 0 .897.055 1.334.163l2.684.667c.79.196 1.343.901 1.343 1.71v.353Z"></path>
        <path fill="currentColor" fill-rule="evenodd" d="M3.474 13h.052c.21 0 .415 0 .59.012.19.013.415.043.65.14a2 2 0 0 1 1.082 1.083c.097.234.127.46.14.65.012.174.012.379.012.588v5.053c0 .21 0 .415-.012.59a2.03 2.03 0 0 1-.14.65 2 2 0 0 1-1.083 1.082c-.234.097-.46.127-.65.14-.174.012-.378.012-.589.012h-.052c-.21 0-.415 0-.59-.012a2.028 2.028 0 0 1-.65-.14 2 2 0 0 1-1.082-1.083 2.03 2.03 0 0 1-.14-.65C1 20.941 1 20.737 1 20.527v-5.054c0-.21 0-.414.012-.588a2.03 2.03 0 0 1 .14-.65 2 2 0 0 1 1.083-1.083 2.03 2.03 0 0 1 .65-.14C3.059 13 3.263 13 3.474 13Z" clip-rule="evenodd"></path>
      </svg>`
    }
  ];
</script>

<section class="py-12 md:py-20 relative overflow-hidden">
  <!-- Background decorative elements -->
  <div class="absolute inset-0 opacity-10">
    <div class="absolute top-20 left-10 w-32 h-32 bg-accent-500/20 rounded-full blur-xl"></div>
    <div class="absolute bottom-20 right-10 w-40 h-40 bg-secondary-500/20 rounded-full blur-xl"></div>
  </div>

  <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <div class="text-left mb-16">
      <p class="text-amber-600 text-xl font-semibold tracking-wider mb-4 ">Be a partner</p>
      <h2 class="text-3xl lg:text-5xl font-bold text-white mb-6">
        CometChat partner<br>
        advantages
      </h2>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each advantages as advantage}
        <div class="group sm:p-4 backdrop-blur-sm   transition-all duration-300    flex flex-col items-start text-left">
          <div class="w-8 h-8 bg-gradient-to-br from-amber-500/20 to-amber-500/20 text-orange-500 rounded-full flex items-center justify-center text-xl mb-6   transition-transform duration-300">
            {@html advantage.icon}
          </div>
          <h3 class="text-base sm:text-xl font-semibold text-white   transition-colors">
            {advantage.title}
          </h3>
          <p class="text-gray-400 font-semibold leading-relaxed">
            {advantage.description}
          </p>
        </div>
      {/each}
    </div>
  </div>
</section>