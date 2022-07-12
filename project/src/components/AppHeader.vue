<template>
  <div>
		<div class="header">
			<div class="logo">
				Netflix
			</div>

			<div class="ricerca">
				<button>Cerca</button>
				<input type="text">
			</div>
		</div>
  </div>
</template>

<script>
export default {
  name: 'AppHeader',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
		.header{
			background-color: black;	
			display: flex;
			align-items: center;
			justify-content: space-between;
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
			}
		}
		
</style>