<script lang="ts">
  let isOpen = false;
  let message = '';

  const toggleChat = () => {
    isOpen = !isOpen;
  };

  const sendMessage = () => {
    if (message.trim()) {
      console.log('Sending message:', message);
      message = '';
    }
  };

  const handleKeyPress = (e: KeyboardEvent) => {
    if (e.key === 'Enter' && !e.shiftKey) {
      e.preventDefault();
      sendMessage();
    }
  };
</script>

<!-- Chat Widget -->
<div class="fixed bottom-6 right-6 z-50">
  {#if isOpen}
    <!-- Chat Window -->
    <div class="mb-4 w-80 h-96 bg-white rounded-2xl shadow-2xl border border-gray-200 flex flex-col overflow-hidden animate-in slide-in-from-bottom-2 fade-in duration-300">
      <!-- Header -->
      <div class="bg-gradient-to-r from-accent-600 to-accent-700 p-4 text-white">
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-3">
            <div class="w-8 h-8 bg-white/20 rounded-full flex items-center justify-center">
              <span class="text-sm">💬</span>
            </div>
            <div>
              <h3 class="font-semibold text-sm">CometChat Support</h3>
              <p class="text-xs opacity-90">Solutions team at CometChat here</p>
            </div>
          </div>
          <button 
            on:click={toggleChat}
            class="text-white/80 hover:text-white transition-colors"
          >
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Messages -->
      <div class="flex-1 p-4 space-y-4 overflow-y-auto">
        <div class="flex items-start space-x-2">
          <div class="w-6 h-6 bg-accent-100 rounded-full flex items-center justify-center text-xs">
            💬
          </div>
          <div class="bg-gray-100 rounded-lg px-3 py-2 max-w-xs">
            <p class="text-sm text-gray-800">
              Hey there! Solutions team at CometChat here. What do you need help with?
            </p>
          </div>
        </div>
      </div>

      <!-- Input -->
      <div class="p-4 border-t border-gray-200">
        <div class="flex space-x-2">
          <input
            type="text"
            bind:value={message}
            on:keypress={handleKeyPress}
            placeholder="Type your message..."
            class="flex-1 px-3 py-2 border border-gray-300 rounded-lg text-sm focus:outline-none focus:ring-2 focus:ring-accent-500 focus:border-transparent"
          />
          <button
            on:click={sendMessage}
            class="bg-accent-600 hover:bg-accent-700 text-white px-4 py-2 rounded-lg transition-colors"
          >
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
  {/if}

  <!-- Chat Button -->
  <button
    on:click={toggleChat}
    class="w-14 h-14 bg-accent-600 hover:bg-accent-700 text-white rounded-full shadow-lg hover:shadow-xl transition-all duration-300 flex items-center justify-center group hover:scale-110"
    aria-label="Open chat"
  >
    {#if isOpen}
      <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="32" height="30" viewBox="0 0 39 37" class="conversations-visitor-open-icon"><defs><path id="conversations-visitor-open-icon-path-1:r0:" d="M31.4824242 24.6256121L31.4824242 0.501369697 0.476266667 0.501369697 0.476266667 24.6256121z"></path></defs><g fill="none" fill-rule="evenodd" stroke="none" stroke-width="1"><g transform="translate(-1432 -977) translate(1415.723 959.455)"><g transform="translate(17 17)"><g transform="translate(6.333 .075)"><path fill="#ffffff" d="M30.594 4.773c-.314-1.943-1.486-3.113-3.374-3.38C27.174 1.382 22.576.5 15.36.5c-7.214 0-11.812.882-11.843.889-1.477.21-2.507.967-3.042 2.192a83.103 83.103 0 019.312-.503c6.994 0 11.647.804 12.33.93 3.079.462 5.22 2.598 5.738 5.728.224 1.02.932 4.606.932 8.887 0 2.292-.206 4.395-.428 6.002 1.22-.516 1.988-1.55 2.23-3.044.008-.037.893-3.814.893-8.415 0-4.6-.885-8.377-.89-8.394"></path></g><g fill="#ffffff" transform="translate(0 5.832)"><path d="M31.354 4.473c-.314-1.944-1.487-3.114-3.374-3.382-.046-.01-4.644-.89-11.859-.89-7.214 0-11.813.88-11.843.888-1.903.27-3.075 1.44-3.384 3.363C.884 4.489 0 8.266 0 12.867c0 4.6.884 8.377.889 8.393.314 1.944 1.486 3.114 3.374 3.382.037.007 3.02.578 7.933.801l2.928 5.072a1.151 1.151 0 001.994 0l2.929-5.071c4.913-.224 7.893-.794 7.918-.8 1.902-.27 3.075-1.44 3.384-3.363.01-.037.893-3.814.893-8.414 0-4.601-.884-8.378-.888-8.394"></path></g></g></g></g></svg>
    {:else}
      <svg class="w-6 h-6 group-hover:scale-110 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"></path>
      </svg>
    {/if}
  </button>
</div>

<style>
  @keyframes slide-in-from-bottom-2 {
    from {
      transform: translateY(0.5rem);
      opacity: 0;
    }
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }

  @keyframes fade-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  .animate-in {
    animation-fill-mode: both;
  }

  .slide-in-from-bottom-2 {
    animation-name: slide-in-from-bottom-2;
  }

  .fade-in {
    animation-name: fade-in;
  }

  .duration-300 {
    animation-duration: 300ms;
  }
</style>