<script>
    export let showContent = false;
</script>

<style>
	.item {
		box-shadow: 0 0 4px #999999;
		border-radius: 10px 10px 0 0;
        margin-bottom: 4px;
	}
	.item-header {
        cursor: pointer;
		background-color: darkslateblue;
        border-radius: 8px 8px 0 0;
		color: white;
		padding: 10px;
        text-align: left;
	}
	.item-content {
        text-align: left;
		background-color: whitesmoke;
		padding: 10px;
        display: none;
	}
    .item-content.active {
        display: block;
    }
</style>

<div class="item">
	<div class="item-header">
		<slot name="header"></slot>
    </div>
	<div class="item-content" class:active={showContent}>
		<slot name="content"></slot>
    </div>
</div>
