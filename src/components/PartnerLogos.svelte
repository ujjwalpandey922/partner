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
    <p class="text-lg font-semibold tracking-wide text-gray-500 text-center opacity-54 mb-8">Trusted by</p>
    <!-- Desktop/Tablet: Static layout -->
    <!-- <div class="hidden md:flex flex-wrap items-center justify-center gap-8 lg:gap-12 opacity-70">
      {#each partners as partner}
        <div class="text-gray-400 hover:text-gray-300 transition-colors duration-300 text-xl font-medium">
          {partner.name}
        </div>
      {/each}
    </div> -->
    <div class=" hidden md:flex w-full flex-col justify-center gap-8" style="--slide-px: -3048px;">
      <div class="flex w-full justify-center gap-8 md:gap-14">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/175x40/5a008cbd85/deloitte-logo.png/m/0x150/" alt="" width="175" height="40">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/800x181/436cd035f4/bitdefender-logo.png/m/0x150/" alt="" width="800" height="181">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/199x40/20574411f2/l-t.png/m/0x150/" alt="" width="199" height="40">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/3000x445/3d90651110/randstad-logo.png/m/0x150/" alt="" width="3000" height="445">
       </div><div class="flex w-full justify-center gap-8 md:gap-14">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/1730x601/3f4b3f5e15/delivery-com-logo.png/m/0x150/" alt="" width="1730" height="601">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/341x72/5cb4bd39f6/shaadi-seeklogo-com-converted-1.png/m/0x150/" alt="" width="341" height="72">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/489x91/8caa394cb6/nb_logo_new_trans.png/m/0x150/" alt="" width="489" height="91">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-50" src="https://a.storyblok.com/f/231922/206x40/752a5ed8aa/geocaching.png/m/0x150/" alt="" width="206" height="40"> </div></div>
    <!-- Mobile: Marquee layout -->
    <div class="md:hidden overflow-hidden">
      <div class="marquee-container">
        <div class="marquee-content gap-8">
          <!-- {#each partners as partner}
            <div class="text-gray-400 text-lg font-medium whitespace-nowrap mx-8">
              {partner.name}
            </div>
          {/each} -->
          <!-- Duplicate for seamless loop -->
          <!-- {#each partners as partner}
            <div class="text-gray-400 text-lg font-medium whitespace-nowrap mx-8">
              {partner.name}
            </div>
          {/each} -->
           <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/175x40/5a008cbd85/deloitte-logo.png/m/0x150/" alt="" width="175" height="40">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/800x181/436cd035f4/bitdefender-logo.png/m/0x150/" alt="" width="800" height="181">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/199x40/20574411f2/l-t.png/m/0x150/" alt="" width="199" height="40">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/3000x445/3d90651110/randstad-logo.png/m/0x150/" alt="" width="3000" height="445">
         <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/1730x601/3f4b3f5e15/delivery-com-logo.png/m/0x150/" alt="" width="1730" height="601">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/341x72/5cb4bd39f6/shaadi-seeklogo-com-converted-1.png/m/0x150/" alt="" width="341" height="72">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/489x91/8caa394cb6/nb_logo_new_trans.png/m/0x150/" alt="" width="489" height="91">
        <img class="animate-fadeIn h-6 w-fit flex-shrink-0 opacity-54" src="https://a.storyblok.com/f/231922/206x40/752a5ed8aa/geocaching.png/m/0x150/" alt="" width="206" height="40">
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
    animation: marquee 3s linear infinite;
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