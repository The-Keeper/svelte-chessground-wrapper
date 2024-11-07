<script lang="ts">
    import { Chessground } from "chessground";
    import type { Config as CGConfig } from "chessground/config";
    import type { Api } from "chessground/api";
    import { onMount } from "svelte";



    let { config = $bindable(), api, ...props }: { config: CGConfig, api: Api } = $props();

    let container: HTMLElement;

    onMount(() => {
        api = Chessground(container, config);
    })
</script>

<div bind:this={container}>
    
</div>