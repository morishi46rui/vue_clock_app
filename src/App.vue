<template>
	<Clock />
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Clock from "./components/ClockScreen.vue";

export default {
	name: "App",
	components: {
		Clock,
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
