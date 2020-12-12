<script>
	export let hdrbg = "darkslateblue";
	export let hdrclr = "white";
	export let fntclr = 'white';
	export let hdrfntsize = '16';
	$: cssVarStyles = `--hdrbg:${hdrbg};
						--hdrclr:${hdrclr};
						--clr:${fntclr};
						--hdrfntsize:${hdrfntsize + 'px'};
						`;
</script>

<style>
	.item {
		box-shadow: 0 0 4px #999999;
		border-radius: 10px 10px 0 0;
        margin-bottom: 4px;
	}
	.item-header {
        cursor: pointer;
		background-color: var(--hdrbg, skyblue);
        border-radius: 8px 8px 0 0;
		color: var(--hdrclr);
		font-size: var(--hdrfntsize);
		padding: 10px;
        text-align: left;
	}
	.item-content {
        text-align: left;
		background-color: whitesmoke;
		padding: 10px;
    }
</style>

<main class="item" style="{cssVarStyles}">
	<div class="item-header">
		<slot name="header"></slot>
    </div>
	<div class="item-content">
		<slot name="content"></slot>
    </div>
</main>
