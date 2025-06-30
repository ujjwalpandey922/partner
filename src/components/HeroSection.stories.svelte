<script lang="ts">
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import HeroSection from './HeroSection.svelte';
</script>

<Meta
  title="Components/HeroSection"
  component={HeroSection}
  parameters={{
    layout: 'fullscreen',
  }}
/>

<Template let:args>
  <HeroSection {...args} />
</Template>

<Story name="Default" />