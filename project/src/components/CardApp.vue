<template>

  <div>
	<div class="card">
		<div class="locandina" v-if="item.poster_path">
			<img :src="`https://image.tmdb.org/t/p/w500${item.poster_path}`" alt="locandina">
		</div>
		<div class="locandina" v-else>
			<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsPr6eGLVtkyoVxMVH9uGBAxOAAr5HMAi1_g&usqp=CAU" alt="sorry">
		</div>
		<div class="informazioni">
			<h2 v-if="item.title">titolo: {{item.title}}</h2>
			<h2 v-else>titolo: {{item.name}}</h2>
			<div class="flag">
				Lingua:
				<img v-if="flagArray.includes(item.original_language)" :src="require(`../assets/img/${item.original_language}.png`)" :alt="language">
				<span v-else>{{ item.original_language }}</span>
				<!-- <div>Voto:{{ item.vote_average }}</div> -->

				<!-- {{ starVote(item.vote_average) }} -->
			</div>
				<div class="voto">
					<span>Voto:</span>
					<i v-for="n in starVote(item.vote_average)" :key="n" class="fas fa-star"></i>
					<i v-for="n in 5 - starVote(item.vote_average)" :key="n" class="far fa-star"></i> 
				</div> 

		</div>

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
			const voteStars = Math.ceil(vote_star / 2);
			return voteStars;
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
		border: 2px solid white;
		margin-left: 10px;
		position: relative;
		img{
			height: 500px;
		}
	}
	.flag{
		width: 40px;
		img{
			height: auto;
		}
	}
	.voto{
		color: white;
	}
	.locandina{
		width: 400px;
	}
	.informazioni{
		background-color: black;
		position: absolute;
		top: 0;
		height: 100%;
		width: 100%;
		opacity: 0;
	}
	.informazioni:hover{
		opacity: 1;
	}


</style>