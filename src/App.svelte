<div class="container">
	<br>
	<p>Pilih juz yang akan diujikan</p>
	<form on:submit|preventDefault={hitung} >
		<center>
			{#each Array(30) as _, n}
				<input type="checkbox" class="checkbox" name="juz" value={n} bind:group={juz} id="juz{n + 1}">
				<label for="juz{n + 1}" class="label btn btn-light">{n + 1}</label>
			{/each}
		</center>
		{#if juz.length != 0}
			<div class="btn btn-warning tombol-kiri" on:click={() => juz = []}>Reset</div>
			<input type="submit" class="btn btn-success tombol" value="Mulai" name="">
		{/if}
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
	.tombol {
		position: fixed;
		right: 20px;
		bottom: 20px;
	}
	.tombol-kiri {
		position: fixed;
		left: 20px;
		bottom: 20px;
	}
</style>
<script type="text/javascript">
	let juz = []
	const hitung = () => {
		if (juz.length != 0) {
			let data = []
			for (let x of juz){
				let list = []
				for (let n = x * 20 + 2; n < x * 20 + 22; n++){
					list.push(n)
				}
				data = [...data, ...list]
			}
			juz.includes(0) ? data = [1, ...data] : ''
			juz.includes(29) ? data = [...data, 602, 603, 604] : ''
			data.sort(() => Math.random() - 0.5)
			let hasil = data[0]
			Swal.fire(`<div>Ujian halaman <strong>${hasil}</strong></div>`)
		}
	}
</script>