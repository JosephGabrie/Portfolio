<script lang="ts">
  import { useDraggable } from "@dnd-kit-svelte/core";
  import { CSS } from "@dnd-kit-svelte/utilities";

  let { class: className = "", ...rest } = $props();

  const { transform, listeners, attributes, node } = useDraggable({
    id: "draggable",
  });

  const style = $derived(
    transform.current
      ? `transform: ${CSS.Translate.toString(transform.current)};`
      : "",
  );
</script>

<div
  class={className}
  style="{style} {rest.style || ''}"
  bind:this={node.current}
  {...listeners.current}
  {...attributes.current}
  {...rest}
>
  <slot>Drag me</slot>
</div>
