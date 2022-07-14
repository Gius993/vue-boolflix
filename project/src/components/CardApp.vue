<template>

  <div>
	<div class="card">
		<!-- <img src="https://mr.comingsoon.it/imgdb/serietv/serie/1947/1947.jpg" alt="prova">		 -->
		<h2 v-if="item.title">titolo: {{item.title}}</h2>
		<h2 v-else>titolo: {{item.name}}</h2>
		<div class="locandina">
			<img :src="`https://image.tmdb.org/t/p/w500${item.poster_path}`" alt="locandina">
		</div>
		<div class="flag">
			Lingua:
			<img v-if="flagArray.includes(item.original_language)" :src="require(`../assets/img/${item.original_language}.png`)" :alt="language">
			<span v-else>{{ item.original_language }}</span>
		</div>
		<!-- <div>Voto:{{ item.vote_average }}</div> -->
		<div>Voto stelle:{{ starVote(item.vote_average) }}</div>

	</div>
		
  </div>
</template>
<script>
/* eslint-disable */
export default {
 	 name: 'CardApp',
	 data:function (){
		return{
			flagArray: ['it', 'en']
		};
	 },
	 methods:{
		starVote(vote_star){
			const voteStars = Math.cell(vote_star);
			// return voteStars / 2;
		}
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
	.locandina{
		width: 400px;
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