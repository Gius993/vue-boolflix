<template>

  <div>
	<div class="card">
		<!-- <img src="https://mr.comingsoon.it/imgdb/serietv/serie/1947/1947.jpg" alt="prova">		 -->
		<h2>titolo: {{item.title}}</h2>
		<!-- <p>Lingua: {{ item.original_language }} </p> -->
		<div class="flag">
			<img v-if="flagArray.includes(item.original_language)" :src="`../assets/img/${item.original_language}.jpg`" >
			<span v-else>{{ item.original_language }}</span>
		</div>
		<p>Voto:{{ item.vote_average }}</p>
	</div>
	<!-- <div class="card-hov">
		<h2>titolo</h2>
		<h2>titolo originale</h2>
		<p>Lingua</p>
		<p>voto</p>
	</div> -->
		
  </div>
</template>
<script>
/* eslint-disable */
export default {
 	 name: 'CardApp',
	 data:function (){
		return{
			flagArray: ["it", "en"]
		};
	 },
	 props:{
		"item": Object
	 },
	 	 
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	/*eslint-disable*/
	.card{
		
		color: white;
		background-color: black;
	
	}
	.flag{
		width: 40px;
	}

	// .card:hover{
	// 	display: none;
	// }
	// .card-hov{
	// 	display: none;
	// }
	// .card-hov:hover {
	// 	width: calc(100% / 3 - 200px);
	// 	height: 500px;
	// 	display: block;
	// 	background-color: black;
	// 	color: white;
	// }
</style>