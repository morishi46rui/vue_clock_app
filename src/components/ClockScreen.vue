<template>
	<div class="container">
		<div class="clock">
			<div class="date">
				<p>{{ year }}/{{ month }}/{{ day }}</p>
			</div>
			<div class="time">
				<p>
					{{ hours }}:{{ minutes }}<span class="seconds">:{{ seconds }}</span>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "ClockScreen",
	data() {
		return {
			date: new Date(),
		};
	},
	computed: {
		year() {
			return this.date.getFullYear();
		},
		month() {
			return this.date.getMonth() + 1;
		},
		day() {
			return this.dateTimePadding(this.date.getDay());
		},
		hours() {
			return this.dateTimePadding(this.date.getHours());
		},
		minutes() {
			return this.dateTimePadding(this.date.getMinutes());
		},
		seconds() {
			return this.dateTimePadding(this.date.getSeconds());
		},
	},
	mounted() {
		this.setDate();
		setInterval(() => this.setDate(), 1000);
	},
	methods: {
		dateTimePadding(num) {
			return ("0" + num).slice(-2);
		},
		setDate() {
			this.date = new Date();
		},
	},
};
</script>

<style scoped>
.container {
	height: 400px;
	width: auto;
	background-color: rgb(22, 39, 33);
	color: aqua;
	font-size: 64px;
	font-weight: 500;
	display: flex;
	justify-content: center;
	align-items: center;
}
</style>
