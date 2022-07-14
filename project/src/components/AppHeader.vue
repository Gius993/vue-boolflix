<template>
  <div>
		<div class="header">
			<div class="logo">
				Netflix
			</div>
			<div class="list">
				<ul>
					<li><a href="#">Home</a></li>
					<li><a href="#">Serie Tv</a></li>
					<li><a href="#">Film</a></li>
					<li><a href="#">Originali</a></li>
					<li><a href="#">Aggiunti di recente</a></li>
					<li><a href="#">La mia lista</a></li>
										
				</ul>
			</div>
			<div class="ricerca">
				<button @click="$emit('performSearch', inputText)">Cerca</button>
				<input type="text"
				v-model="inputText"
				@keyup.enter="$emit('performSearch', inputText)"
				>
			</div>
		</div>
  </div>
</template>

<script>
export default {
  name: 'AppHeader',
	data: function(){
		return{
			inputText: ''
		}
	}	
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

		.header{
			background-color: black;	
			display: flex;
			align-items: center;
			justify-content: space-evenly;
			padding: 40px;
		}
		.logo{
			color: red;
			font-size: 60px;
			
		}
		.ricerca{
			display: flex;
			align-items: center;
			input{
				width: 15vw;
				height: 40px;
				font-size: 40px;
			}
			button{
				width: 100px;
				height: 40px;
				background-color: red;
				border: 1px solid white;
			}
		}
		.list{
			ul{
				display: flex;
			}
			li{
				margin-left: 40px;
			}
			a{
				color: white;
				font-size: 25px;
			}
		}
		
</style>