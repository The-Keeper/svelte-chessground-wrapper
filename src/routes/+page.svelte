<script lang="ts">
    import Chessground from "$lib/Chessground.svelte";
    import type { Api } from "chessground/api";
    import type { Config } from "chessground/config";
    import { onMount } from "svelte";

    let api: Api = $state(null as unknown as Api);
    let config: Config = $state({});

onMount(() => {
    $inspect(api)
    $inspect(config)
})

</script>

<button onclick={ () => { 
            config = { fen: 'rnbqkbnr/pppppppp/8/8/4P3/8/PPPP1PPP/RNBQKBNR b KQkq e3 0 1' }
} }> setting </button>
<button onclick={ () => {
    api.set({fen: `rnbqkbnr/pp1ppppp/8/2p5/4P3/8/PPPP1PPP/RNBQKBNR w KQkq c6 0 2`})
} }> api </button>

<Chessground {config} {api}></Chessground>
