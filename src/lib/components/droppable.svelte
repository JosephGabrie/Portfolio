<script lang="ts">
  import { useDroppable } from "@dnd-kit-svelte/core";

  let { class: className = "" } = $props();

  const { isOver, node } = useDroppable({
    id: "droppable",
  });
</script>

<div
  bind:this={node.current}
  class={className || `flex h-32 w-full items-center justify-center rounded-lg border-2 border-dashed border-gray-300 p-4 transition-colors ${isOver.current ? 'bg-green-100 border-green-500' : ''}`}
>
  <slot>
    <p class="text-gray-500">Drop here</p>
  </slot>
</div>
