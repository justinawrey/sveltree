<script>
  export let toggleOpen;
  export let title;
  export let open;
  export let level = 0;

  $: indentation = level * 15;
  $: rotation = open ? "90" : "0";
</script>

<button style="margin-left: {indentation}px" on:click={toggleOpen}>
  <svg
    style="transform: rotate({rotation}deg); transition: transform 100ms"
    xmlns="http://www.w3.org/2000/svg"
    width="8"
    height="8"
    viewBox="0 0 24 24"><path
      d="M7.33 24l-2.83-2.829 9.339-9.175-9.339-9.167 2.83-2.829 12.17 11.996z" /></svg>
  {title}
</button>
