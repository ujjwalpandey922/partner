<script lang="ts">
  import Header from './components/Header.svelte';
  import HeroSection from './components/HeroSection.svelte';
  import PartnerLogos from './components/PartnerLogos.svelte';
  import PartnerAdvantages from './components/PartnerAdvantages.svelte';
  import PartnershipPrograms from './components/PartnershipPrograms.svelte';
  import CallToAction from './components/CallToAction.svelte';
  import Footer from './components/Footer.svelte';
  import ChatWidget from './components/ChatWidget.svelte';
</script>

<svelte:head>
  <title>CometChat Partner Program - Join Our Partner Universe</title>
  <meta name="description" content="Create value for your clients with CometChat's world-class technology. Join our partner program and grow your business with free credits, revenue share, and exclusive benefits." />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div class="min-h-screen bg-company-700 font-sans">
  <Header />
  <main>
    <HeroSection />
    <PartnerLogos />
    <PartnerAdvantages />
    <PartnershipPrograms />
    <CallToAction />
  </main>
  <Footer />
  <ChatWidget />
</div>