<template>
<!-- eslint-disable -->
	<div>
		<div class="main-container">				
			<CardApp />			
		</div>
	</div>
</template>

<script>
/* eslint-disable */
import axios from "axios";
import CardApp from "./CardApp.vue";
export default {
    name: "AppMain",
    componets: {
        CardApp
    },
    data() {
        return {
            card: []
        };
    },
    created() {
        this.getFilm();
    },
    methods: {
        getFilm() {
            axios
                .get("https://api.themoviedb.org/3/movie/550?api_key=4961c6668a6a7f12b27a2f288b02c0eb");
        }
    },
    components: { CardApp }
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
