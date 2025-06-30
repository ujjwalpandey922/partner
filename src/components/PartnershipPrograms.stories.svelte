<script lang="ts">
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import PartnershipPrograms from './PartnershipPrograms.svelte';
</script>

<Meta
  title="Components/PartnershipPrograms"
  component={PartnershipPrograms}
  parameters={{
    layout: 'fullscreen',
  }}
/>

<Template let:args>
  <PartnershipPrograms {...args} />
</Template>

<Story name="Default" />