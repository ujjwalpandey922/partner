<script lang="ts">
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import CallToAction from './CallToAction.svelte';
</script>

<Meta
  title="Components/CallToAction"
  component={CallToAction}
  parameters={{
    layout: 'fullscreen',
  }}
/>

<Template let:args>
  <CallToAction {...args} />
</Template>

<Story name="Default" />

<Story 
  name="Custom Content" 
  args={{
    title: "Ready to get started?",
    description: "Join thousands of developers building amazing chat experiences.",
    primaryButton: "Get Started",
    secondaryButton: "View Pricing"
  }}
/>