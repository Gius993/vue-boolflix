<template>
	<div>
		<div class="main-container">
			<div class="card">
				<img src="https://mr.comingsoon.it/imgdb/serietv/serie/1947/1947.jpg" alt="prova">
			</div>
			<!-- <div class="card-hov">
				<h1>titolo</h1>
				<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis, reiciendis cumque optio corrupti min</p>
			</div> -->
				<div class="card">
				<img src="https://mr.comingsoon.it/imgdb/serietv/serie/1947/1947.jpg" alt="prova">
			</div>
			<!-- <div class="card-hov">
				<h1>titolo</h1>
				<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis, reiciendis cumque optio corrupti min</p>
			</div> -->
				<div class="card">
				<img src="https://mr.comingsoon.it/imgdb/serietv/serie/1947/1947.jpg" alt="prova">
			</div>
			<!-- <div class="card-hov">
				<h1>titolo</h1>
				<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis, reiciendis cumque optio corrupti min</p>
			</div> -->
		</div>
	</div>
</template>

<script>
export default {
  name: 'HelloWorld',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	@import "../assets/style/variables.scss";
	.main-container{
		width: 100vw;
		padding: 200px;
		display: flex;
		justify-content: space-around;
	}
	.card{
		width: calc(100% / 3 - 200px);
	}
	// .card:hover{
	// 	display: none;
	// }
	// .card-hov{
	// 	display: none;
	// }
	// .card-hov:hover {
	// 	display: block;
	// 	background-color: black;
	// 	color: white;
	// }
</style>
