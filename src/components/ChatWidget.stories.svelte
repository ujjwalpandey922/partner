<script lang="ts">
  import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
  import ChatWidget from './ChatWidget.svelte';
</script>

<Meta
  title="Components/ChatWidget"
  component={ChatWidget}
  parameters={{
    layout: 'fullscreen',
  }}
/>

<Template let:args>
  <div style="height: 100vh; position: relative;">
    <ChatWidget {...args} />
  </div>
</Template>

<Story name="Default" />