<template>
<!-- eslint-disable -->
	<div>
		<div class="main-container" v-if="movieCards.length">				
			<div class="list-title">
				<CardApp
				v-for="card in movieCards"
				:key="card.id"
				:item="card"
				/>	
				
			</div>
			<div class="list-title serie">
				
				<CardApp
				v-for="card in seriesCards"
				:key="card.id"
				:item="card"
				/>			
			</div>
		</div>
	</div>
</template>

<script>
/* eslint-disable */
// import axios from "axios";
import CardApp from "./CardApp.vue";
export default {
    name: "AppMain",
    props: {
        "movieCards": Array,
		"seriesCards": Array,
        "searching": Boolean
    },
    components: {
        CardApp
    }
 };

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

	@import "../assets/style/variables.scss";
	.main-container{	
		display: flex;
		flex-direction: column;
		justify-content: space-around;
	}
	.list-title{
		margin-top: 200px;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		overflow-x: auto;
	}


</style>
