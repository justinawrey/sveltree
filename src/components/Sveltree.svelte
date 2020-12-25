<script>
  import { slide } from "svelte/transition";
  import DefaultInternalNode from "./DefaultInternalNode.svelte";
  import DefaultLeaf from "./DefaultLeaf.svelte";

  export let nodes = [];
  export let level = 0;

  const openStates = Array(nodes.length).fill(false);
  const toggleOpenStateAt = (index) => () => {
    openStates[index] = !openStates[index];
  };

  function isLeaf(node) {
    return !node.nodes;
  }

  $: duration = Math.min(nodes.length * 100, 300);
</script>

<style>
  .reset {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
</style>

<ul class="reset">
  {#each nodes as node, i (node.title)}
    <li transition:slide={{ duration }}>
      {#if isLeaf(node)}
        <slot name="leaf" title={node.title} {level}>
          <DefaultLeaf title={node.title} {level} />
        </slot>
      {:else}
        <slot
          name="internalNode"
          toggleOpen={toggleOpenStateAt(i)}
          open={openStates[i]}
          title={node.title}
          {level}>
          <DefaultInternalNode
            toggleOpen={toggleOpenStateAt(i)}
            open={openStates[i]}
            title={node.title}
            {level} />
        </slot>
      {/if}
      {#if openStates[i]}
        <svelte:self
          nodes={node.nodes}
          level={level + 1}
          let:toggleOpen
          let:open
          let:title
          let:level>
          <slot {toggleOpen} {open} {title} {level}>
            <DefaultInternalNode {toggleOpen} {open} {title} {level} />
          </slot>
        </svelte:self>
      {/if}
    </li>
  {/each}
</ul>
