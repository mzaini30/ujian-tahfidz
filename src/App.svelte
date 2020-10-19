<div class="container">
	<br>
	<p>Pilih juz yang akan diujikan</p>
	<form>
		<center>
			{#each Array(30) as _, n}
				<input type="checkbox" class="checkbox" name="juz" id="juz{n + 1}">
				<label for="juz{n + 1}" class="label btn btn-light">{n + 1}</label>
			{/each}
		</center>
	</form>
</div>
<style type="text/css">
	.label {
		border-radius: 50%;
		font-size: 30px;
		margin: 0 10px 10px 0;
	}
	.checkbox:checked + .label {
		background: var(--dark);
		border-color: var(--dark);
		color: white;
	}
	.checkbox {
		position: absolute;
		left: -100vw;
	}
</style>
