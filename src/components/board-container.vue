<template>
<div class="board-cont">
	<h5>{{boardHeader}}</h5>
	<ul>
		<!-- Set Loop here to add more cards as per data from owner -->
		<li v-for="index in cards" v-bind:key = "index" :id="boardName + '_li_' + index" >
			<card v-bind:id="'card' + index" :index="boardName + '_li_' + index" :order-status="boardHeader" ></card>
		</li>
	</ul>
</div>
</template>

<script>
import card from './card.vue'

export default {
  name: 'board-container',
  
  components: {
	card
  },
  props: {
	boardHeader : String, //default value determined from board-header attribute in the component
	cards: Number,
	boardName : String,
  }
}
</script>
<style>
.board-cont{
	background-color: #F4F4F4;
	padding: 2px 1.5rem 5px 1.5rem;
	min-height: 1000px;
	max-height: 2000px;
	overflow: auto;
	border-radius: .3rem;
}

.board-cont > h5 {
	color: #A0A0A0;
}

.board-cont > ul {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
	grid-gap: 1rem;
}
</style>
