<script>
    export let label = '';
    export let opendialog = false;
</script>

<style>
    .overlay { 
		position: fixed;
		z-index: 900;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
		background-color: rgba(200,200,200,0.8);
		display: none;
	}
	.overlay.active {
		display: block;
	}
	.dialog-box {
		position: fixed;
		z-index: 999;
		left: 20%;
		right: 20%;
		top: 10%;
		bottom: 10%;
		padding: 20px;
        overflow-y: auto;
		box-shadow: 0 0 10px #666666;
		background-color: #ffffff;
		border-radius: 20px;
	}
    .dialog-header {
        display: grid;
        grid-template-columns: 1fr auto;
        gap: 10px;
        align-items: center;
		font-family: Orbitron;
		box-shadow: 0 2px 0 #999999;
    }
    .dialog-content {
		position: relative;
		top: 1vh;
		left: 1vw;
		right: 1vw;
		height: 60vh;
		overflow-y: auto;
	}
  @media screen and (max-width: 639px) {
    .dialog-box {
        padding: 0 4px 0 10px;
        margin: 0;
		left: 1vw;
		right: 1vw;
    }
  }
</style>

<div class="overlay" class:active={opendialog}>
    <div class="dialog-box">
        <div class="dialog-header">
            <h3>{label}</h3>
            <button class="icon-btn" on:click>&times;</button>
        </div>
        <div class="dialog-content">
            <slot></slot>
        </div>
    </div>
</div>