<script lang="ts">
    import Chessground from "$lib/Chessground.svelte";
    import type { CGConfig, CGApi } from "$lib/Chessground";

    let api: CGApi = $state(null as unknown as CGApi);
    let config: CGConfig = $state({});

    // $inspect(api);
</script>

<button
    onclick={() => {
        config = {
            fen: "rnbqkbnr/pppppppp/8/8/4P3/8/PPPP1PPP/RNBQKBNR b KQkq e3 0 1",
        };
    }}
>
    setting
</button>
<button
    onclick={() => {
        api.move("e7", "e5");
    }}
>
    api
</button>

<button
    onclick={() => {
        console.log(api.getFen())
    }}
>
    fen
</button>

<div style="width: 500px;">
    <Chessground bind:config />
</div>