<script lang="ts">
  let formData = {
    firstName: '',
    lastName: '',
    email: '',
    phone: '',
    message: ''
  };

  const handleSubmit = (e: Event) => {
    e.preventDefault();
    console.log('Form submitted:', formData);
    // Handle form submission logic here
  };
</script>

<section class="relative min-h-screen py-8 flex items-center justify-center overflow-hidden bg-company-200">
  <!-- Decorative gradient orbs -->
  <div class="gradient-orb gradient-orb-1"></div>
  <div class="gradient-orb gradient-orb-2"></div>
  <div class="gradient-orb gradient-orb-3"></div>
  
  <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-20 relative z-10">
    <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-start justify-center">
      <!-- Left Column - Content -->
      <div class="text-center lg:text-left lg:pl-16 lg:pt-16">
        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-semibold text-white mb-6 leading-tight">
          Join the CometChat<br>
          partner universe
        </h1>
        <p class="text-xl text-gray-300 mb-8 leading-relaxed font-semibold max-w-xl mx-auto lg:mx-0">
          Create value for your clients, leveraging our world-class technology. Partner with us and grow your business!
        </p>
      </div>

      <!-- Right Column - Form -->
      <div class="max-w-lg w-full mx-auto">
        <div class=" bg-dark-800/20 backdrop-blur-2xl rounded-3xl p-8 border border-dark-700/50 shadow-2xl">
          <h2 class="text-2xl font-bold text-white mb-6">Become a partner</h2>
          
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
                required
                class="w-full px-4 py-3 bg-dark-800/20  border border-dark-300/20 rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all"
              />
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
                required
                class="w-full px-4 py-3 bg-dark-800/20  border border-dark-300/20 rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all"
              />
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
                required
                class="w-full px-4 py-3 bg-dark-800/20  border border-dark-300/20 rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all"
              />
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
                class="w-full px-4 py-3 bg-dark-800/20  border border-dark-300/20 rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all"
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
                required
                class="w-full px-4 py-3 bg-dark-800/20  border border-dark-300/20 rounded-xl text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent transition-all resize-none"
              ></textarea>
            </div>

            <button
              type="submit"
              class="w-max bg-accent-600 hover:bg-accent-700 text-white font-medium py-3 px-6 rounded-xl transition-all duration-300 hover:shadow-lg hover:shadow-accent-500/25 transform hover:scale-105"
            >
              Send Message
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</section>