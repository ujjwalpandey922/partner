<script lang="ts">
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import Header from './Header.svelte';
</script>

<Meta
  title="Components/Header"
  component={Header}
  parameters={{
    layout: 'fullscreen',
  }}
/>

<Template let:args>
  <Header {...args} />
</Template>

<Story name="Default" />

<Story name="Scrolled" args={{ scrolled: true }} />