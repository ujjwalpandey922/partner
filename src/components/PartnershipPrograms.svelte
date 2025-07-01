<script lang="ts">
  const programs = [
    {
      title: 'Affiliate partner program',
      description: 'Bring value to your customers with a world-class in-app messaging tool that increases user-to-user engagement and retention. Get incentivized for referring CometChat to any of your customers.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="w-4 h-4"><path fill="#6851d6" fill-rule="evenodd" d="M15.134 2.154a4.832 4.832 0 0 0-6.268 0 2.832 2.832 0 0 1-1.612.668 4.832 4.832 0 0 0-4.432 4.432 2.832 2.832 0 0 1-.668 1.612 4.832 4.832 0 0 0 0 6.268c.387.454.62 1.018.668 1.612a4.832 4.832 0 0 0 4.432 4.432 2.832 2.832 0 0 1 1.612.668 4.832 4.832 0 0 0 6.268 0 2.832 2.832 0 0 1 1.612-.668 4.832 4.832 0 0 0 4.432-4.432 2.832 2.832 0 0 1 .668-1.612 4.832 4.832 0 0 0 0-6.268 2.832 2.832 0 0 1-.668-1.612 4.832 4.832 0 0 0-4.432-4.432 2.832 2.832 0 0 1-1.612-.668Zm1.073 8.053a1 1 0 0 0-1.414-1.414L11 12.586l-1.293-1.293a1 1 0 0 0-1.414 1.414l2 2a1 1 0 0 0 1.414 0l4.5-4.5Z" clip-rule="evenodd"/></svg>`,
      color: 'from-accent-500 to-accent-600'
    },
    {
      title: 'Technology partner program',
      description: 'Development teams can use our plug and play solution to build top class chat solutions for their clients using our SDKs and APIs. It\'s simple, safe and secure!',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="w-4 h-4"><path fill="#6851d6" fill-rule="evenodd" d="M17.838 2H6.162c-.527 0-.981 0-1.356.03-.395.033-.789.104-1.167.297a3 3 0 0 0-1.311 1.311c-.193.378-.264.772-.296 1.167C2 5.18 2 5.635 2 6.161V17.84c0 .527 0 .982.03 1.356.033.395.104.789.297 1.167a3 3 0 0 0 1.311 1.311c.378.193.772.264 1.167.296.375.031.83.031 1.356.031H17.84c.527 0 .982 0 1.356-.03.395-.033.789-.104 1.167-.297a3 3 0 0 0 1.311-1.311c.193-.378.264-.772.296-1.167.031-.375.031-.83.031-1.356V6.16c0-.527 0-.981-.03-1.356-.033-.395-.104-.789-.297-1.167a3 3 0 0 0-1.311-1.311c-.378-.193-.772-.264-1.167-.296A17.9 17.9 0 0 0 17.838 2Zm-7.13 5.707a1 1 0 0 0-1.415-1.414l-3 3a1 1 0 0 0 0 1.414l3 3a1 1 0 0 0 1.414-1.414L8.414 10l2.293-2.293Zm4 2.586a1 1 0 1 0-1.415 1.414L15.586 14l-2.293 2.293a1 1 0 0 0 1.414 1.414l3-3a1 1 0 0 0 0-1.414l-3-3Z" clip-rule="evenodd"></path></svg>`,
      color: 'from-accent-500 to-accent-600'
    },
    {
      title: 'Start up growth program',
      description: 'We help incubators, accelerators, co-working space that focus on recognition of start-ups. This program also enables VCs to accelerate the growth of their portfolio companies.',
      icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="w-4 h-4"><path fill="#6851d6" d="M12 2a1 1 0 0 1 1 1v2a1 1 0 1 1-2 0V3a1 1 0 0 1 1-1ZM4 19a1 1 0 0 1 1-1h14a1 1 0 1 1 0 2H5a1 1 0 0 1-1-1Zm.607-13.807a1 1 0 1 0-1.414 1.414l1.414 1.414a1 1 0 1 0 1.414-1.414L4.607 5.193Zm16.2 0a1 1 0 0 1 0 1.414l-1.414 1.414a1 1 0 1 1-1.414-1.414l1.414-1.414a1 1 0 0 1 1.414 0ZM5.07 14a7.002 7.002 0 0 1 13.86 0H22a1 1 0 1 1 0 2H2a1 1 0 1 1 0-2h3.07Z"></path></svg>`,
      color: 'from-accent-500 to-accent-600'
    }
  ];
</script>


<section class="py-12 md:py-20 bg-white relative">
  <!-- Background pattern -->
  <div class="absolute inset-0 opacity-5">
    <div class="absolute inset-0" style="background-image: radial-gradient(circle at 1px 1px, rgba(255,255,255,0.15) 1px, transparent 0); background-size: 20px 20px;"></div>
  </div>

  <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <div class="text-left sm:px-4 md:text-center mb-16">
      <p class="text-accent-500 text-xl font-bold leading-tighter mb-4">Our programs</p>
      <h2 class="text-3xl lg:text-5xl leading-tighter font-bold text-dark-800 mb-6">
        Types of partnerships<br>
        programs
      </h2>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
      {#each programs as program}
        <div class="group bg-white rounded-2xl p-2 transition-all duration-500">
          <div class="mb-1">
            <div class="w-9 h-9 bg-accent-100 rounded-full flex items-center justify-center text-xl mb-2 transition-transform duration-300">
               {@html program.icon}
            </div>
            <h3 class="text-xl font-bold text-dark-800 transition-colors">
              {program.title}
            </h3>
          </div>
          <p class="text-dark-800 font-medium leading-snug tracking-wide opacity-70">
            {program.description}
          </p>
        </div>
      {/each}
    </div>
  </div>
</section>