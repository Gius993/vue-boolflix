<template>

  <div>
	<div class="card">
		<div class="locandina">
			<img :src="`https://image.tmdb.org/t/p/w500${item.poster_path}`" alt="locandina">
		</div>
		<div class="informazioni">
			<h2 v-if="item.title">titolo: {{item.title}}</h2>
			<h2 v-else>titolo: {{item.name}}</h2>
			<div class="flag">
				Lingua:
				<img v-if="flagArray.includes(item.original_language)" :src="require(`../assets/img/${item.original_language}.png`)" :alt="language">
				<span v-else>{{ item.original_language }}</span>
				<div>Voto:{{ item.vote_average }}</div>
			</div>

		</div>
		<!-- <div>Voto stelle:{{ starVote(item.vote_average) }}</div> -->

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
	//  methods:{
	// 	starVote(vote_star){
	// 		const voteStars = Math.cell(vote_star);
	// 		return voteStars / 2;
	// 	}
	//  },
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
		border: 2px solid white;
		margin-left: 10px;
		img{
			height: 500px;
		}
	}
	.flag{
		width: 40px;
	}
	.locandina{
		width: 400px;
	}
	.informazioni{
		background-color: black;
		display: none;
	}
	.informazioni:hover{
		display: block;
	}
	.locandina:hover{
		img{

			display: none;
		}
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