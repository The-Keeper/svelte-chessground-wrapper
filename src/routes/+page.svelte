<script lang="ts">
    import Chessground from "$lib/Chessground.svelte";
    import type { Api } from "chessground/api";
    import type { Config } from "chessground/config";
    import { onMount } from "svelte";

    let api: Api = $state(null as unknown as Api);
    let config: Config = $state({});

onMount(() => {
})

$inspect(api);

</script>

<button onclick={ () => { 
            config = { fen: 'rnbqkbnr/pppppppp/8/8/4P3/8/PPPP1PPP/RNBQKBNR b KQkq e3 0 1' }
} }> setting </button>
<button onclick={ () => {
    api.move("e7", "e5")
} }> api </button>

<div style="width: 500px;">
    <Chessground {config} {api}></Chessground>
</div>
