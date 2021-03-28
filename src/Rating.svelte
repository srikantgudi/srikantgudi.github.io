<script>
    export let text;
    export let rating;
</script>
<style>
	.skill-name {
		font-weight: 600;
		text-transform: uppercase;
	}
    .bg {
        background-color: #ced4da;
        padding: 8px;
    }
    .progress {
        width: 100%;
    }
</style>
<div class="bg">
    <div class="skill-name">{text}</div>
    <div>
        <progress class="progress" max="10" value={rating} />
    </div>
</div>