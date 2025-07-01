<script lang="ts">
  export let title = "Start building today";
  export let description = "Build faster, scale smarter, and elevate your chat experience with tools that grow with your business.";
  export let primaryButton = "Start for free";
  export let secondaryButton = "Schedule a demo";
</script>

<section class="py-32 bg-comapny-700 relative overflow-hidden">
  <!-- Decorative gradient orbs -->
  <div class="absolute top-10 left-10 w-64 h-64 bg-gradient-to-br from-accent-500/30 to-primary-500/30 rounded-full blur-3xl animate-float"></div>
  <div class="absolute bottom-10 right-10 w-48 h-48 bg-gradient-to-br from-secondary-500/30 to-accent-500/30 rounded-full blur-2xl animate-float" style="animation-delay: -2s;"></div>
  
  <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <div class="text-left md:text-center max-w-3xl mx-auto">
      <h2 class="text-4xl lg:text-5xl font-bold text-white mb-6">
        {title}
      </h2>
      <p class="text-xl text-gray-300 mb-12 leading-relaxed">
        {description}
      </p>
      
      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <button class="bg-accent-600 hover:bg-accent-700 text-white font-medium px-8 py-4 rounded-lg transition-all duration-300 hover:shadow-lg hover:shadow-accent-500/25 transform hover:scale-105">
          {primaryButton}
        </button>
        <button class="border border-gray-600 hover:border-gray-500 text-white font-medium px-8 py-4 rounded-lg transition-all duration-300 hover:bg-dark-800">
          {secondaryButton}
        </button>
      </div>
    </div>
  </div>
</section>