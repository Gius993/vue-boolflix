<template>
<!-- eslint-disable -->
	<div>
		<div class="main-container" v-if="movieCards.length">				
			<CardApp
            v-for="card in movieCards"
            :key="card.id"
            :item="card"
            />			
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
		width: 100vw;
		padding: 200px;
		display: flex;
		justify-content: space-around;
	}

</style>
