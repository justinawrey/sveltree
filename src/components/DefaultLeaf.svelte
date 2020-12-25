<script>
  export let title;
  export let level = 0;

  $: indentation = level * 15;
</script>

<p style="margin: 0 0 0 {indentation}px">{title}</p>
