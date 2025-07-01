<script lang="ts">
  let formData = {
    firstName: '',
    lastName: '',
    email: '',
    phone: '',
    message: ''
  };

  let errors = {
    firstName: '',
    lastName: '',
    email: '',
    message: ''
  };

  let isSubmitted = false;
  let isLoading = false;

  const validateForm = () => {
    let isValid = true;
    
    // Reset errors
    errors = {
      firstName: '',
      lastName: '',
      email: '',
      message: ''
    };

    // Validate each field
    if (!formData.firstName.trim()) {
      errors.firstName = 'First name is required';
      isValid = false;
    }

    if (!formData.lastName.trim()) {
      errors.lastName = 'Last name is required';
      isValid = false;
    }

    if (!formData.email.trim()) {
      errors.email = 'Email is required';
      isValid = false;
    } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(formData.email)) {
      errors.email = 'Please enter a valid email';
      isValid = false;
    }

    if (!formData.message.trim()) {
      errors.message = 'Message is required';
      isValid = false;
    }

    return isValid;
  };

  const handleSubmit = async (e: Event) => {
    e.preventDefault();
    
    if (validateForm()) {
      isLoading = true;
      
      // Simulate API call
      await new Promise(resolve => setTimeout(resolve, 1000));
      
      console.log('Form submitted:', formData);
      isSubmitted = true;
      isLoading = false;
      
      // Optional: Reset form
      formData = {
        firstName: '',
        lastName: '',
        email: '',
        phone: '',
        message: ''
      };
    } else {
      console.log('Form has errors', errors);
    }
  };
</script>

<section class="relative min-h-screen py-8 flex items-center justify-center overflow-hidden bg-company-700">
  <!-- Decorative gradient orbs -->
  <div class="gradient-orb gradient-orb-1"></div>
  <div class="gradient-orb gradient-orb-2"></div>
  <div class="gradient-orb gradient-orb-3"></div>
  
  <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-20 relative z-10">
    <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-start justify-center">
      <!-- Left Column - Content -->
      <div class="text-left lg:pl-16 lg:pt-16">
        <h1 class="text-3xl sm:text-5xl lg:text-6xl font-semibold text-white mb-6 leading-tight">
          Join the CometChat<br>
          partner universe
        </h1>
        <p class="text-xl text-gray-300 mb-4 sm:mb-8 leading-none sm:leading-relaxed font-semibold max-w-xl mx-auto lg:mx-0">
          Create value for your clients, leveraging our world-class technology. Partner with us and grow your business!
        </p>
      </div>

      <!-- Right Column - Form -->
      <div class="max-w-lg w-full mx-auto">
        <div class="bg-dark-800/20 backdrop-blur-2xl rounded-3xl p-4 sm:p-8 border border-dark-700/50 shadow-2xl">
          {#if !isSubmitted}
            <h2 class="text-2xl font-bold text-white mb-6">Became a partner</h2>
            
            <form on:submit={handleSubmit} class="space-y-6">
              <div>
                <label for="firstName" class="block text-sm font-medium text-gray-300 mb-2">
                  First name*
                </label>
                <input
                  type="text"
                  id="firstName"
                  bind:value={formData.firstName}
                  placeholder="First Name"
                  class={`w-full px-4 py-3 bg-dark-800/20 border ${errors.firstName ? 'border-red-500' : 'border-dark-300/20'} rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all`}
                />
                {#if errors.firstName}
                  <p class="mt-1 text-sm text-red-500">{errors.firstName}</p>
                {/if}
              </div>

              <div>
                <label for="lastName" class="block text-sm font-medium text-gray-300 mb-2">
                  Last name*
                </label>
                <input
                  type="text"
                  id="lastName"
                  bind:value={formData.lastName}
                  placeholder="Last Name"
                  class={`w-full px-4 py-3 bg-dark-800/20 border ${errors.lastName ? 'border-red-500' : 'border-dark-300/20'} rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all`}
                />
                {#if errors.lastName}
                  <p class="mt-1 text-sm text-red-500">{errors.lastName}</p>
                {/if}
              </div>

              <div>
                <label for="email" class="block text-sm font-medium text-gray-300 mb-2">
                  Email*
                </label>
                <input
                  type="email"
                  id="email"
                  bind:value={formData.email}
                  placeholder="Your Business Email"
                  class={`w-full px-4 py-3 bg-dark-800/20 border ${errors.email ? 'border-red-500' : 'border-dark-300/20'} rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all`}
                />
                {#if errors.email}
                  <p class="mt-1 text-sm text-red-500">{errors.email}</p>
                {/if}
              </div>

              <div>
                <label for="phone" class="block text-sm font-medium text-gray-300 mb-2">
                  Phone
                </label>
                <input
                  type="tel"
                  id="phone"
                  bind:value={formData.phone}
                  placeholder="+1 7201234567"
                  class="w-full px-4 py-3 bg-dark-800/20 border border-dark-300/20 rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all"
                />
              </div>

              <div>
                <label for="message" class="block text-sm font-medium text-gray-300 mb-2">
                  Message*
                </label>
                <textarea
                  id="message"
                  bind:value={formData.message}
                  placeholder="How can we help you?"
                  rows="4"
                  class={`w-full px-4 py-3 bg-dark-800/20 border ${errors.message ? 'border-red-500' : 'border-dark-300/20'} rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all`}
                ></textarea>
                {#if errors.message}
                  <p class="mt-1 text-sm text-red-500">{errors.message}</p>
                {/if}
              </div>

              <button
                type="submit"
                class="w-max bg-accent-600 hover:bg-accent-700 text-white font-medium py-3 px-6 rounded-xl transition-all duration-300 hover:shadow-lg hover:shadow-accent-500/25 transform hover:scale-105 disabled:opacity-50 disabled:cursor-not-allowed"
                disabled={isLoading}
              >
                {#if isLoading}
                  <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white inline" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                  </svg>
                  Sending...
                {:else}
                  Send Message
                {/if}
              </button>
            </form>
          {:else}
            <div class="text-center py-8">
              <svg class="mx-auto h-16 w-16 text-green-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
              <h2 class="text-2xl font-bold text-white mt-4 mb-2">Thank you!</h2>
              <p class="text-gray-300 mb-6">Your message has been sent successfully.</p>
              <button
                on:click={() => isSubmitted = false}
                class="w-max bg-accent-600 hover:bg-accent-700 text-white font-medium py-2 px-4 rounded-lg transition-all duration-300"
              >
                Send another message
              </button>
            </div>
          {/if}
        </div>
      </div>
    </div>
  </div>
</section>