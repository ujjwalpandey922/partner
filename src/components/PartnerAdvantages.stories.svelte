<script lang="ts">
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import PartnerAdvantages from './PartnerAdvantages.svelte';
</script>

<Meta
  title="Components/PartnerAdvantages"
  component={PartnerAdvantages}
  parameters={{
    layout: 'fullscreen',
  }}
/>

<Template let:args>
  <PartnerAdvantages {...args} />
</Template>

<Story name="Default" />