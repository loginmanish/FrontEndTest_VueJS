<template>
<div class="boards">
	<ul>
		<li>
			<board-container v-bind:board-header="'NEW ORDERS'" v-bind:cards="2" v-bind:board-name="'bNO'" ></board-container>
		</li>
		<li>
			<board-container v-bind:board-header="'IN PROGRESS'" v-bind:cards="2" v-bind:board-name="'bIP'"></board-container>
		</li>
		<li>
			<board-container v-bind:board-header="'WAITING FOR BUYER'" v-bind:cards="1" v-bind:board-name="'bWFB'"></board-container>
		</li>
		<li>
			<board-container v-bind:board-header="'COMPLETED'" v-bind:cards="3" v-bind:board-name="'bC'"></board-container>
		</li>
	</ul>
</div>
</template>
<script>
import boardContainer from './board-container.vue'

export default {
  name: 'boards',
  components: {
    'board-container' : boardContainer
  }
}
</script>
<style>
.boards > ul {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
	grid-gap: 2rem;
	background-color: #FAFCFE;
}
</style>