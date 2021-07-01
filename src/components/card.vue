<template>
<div class="card">
	<card-menu @hideCard="hideMe" v-bind:card-id="index"></card-menu>
	<card-order-details :product-image="'F_Purse3_drop.jfif'" :order-status="status()" :timer-time-text="'5 days left'" :info-hrs="'20 hrs'" :info-amt="'$320'"></card-order-details>
	<card-view-order :user-image-file="'usr1.png'"></card-view-order>
</div>
</template>
<script>
import cardMenu from './card-menu.vue'
import cardOrderDetails from './card-order-details.vue'
import cardViewOrder from './card-view-order.vue'
var counter = 0;
export default {
  name: 'card',
  data: function () {
	return {
		counter : 0
	}
  },
  props: {
		index : String,
		orderStatus : String,
		timerTimeText : String,
		infoHrs: String, 
		showInfoHours: String, 
		infoAmt: String, 
	},
  components: {
	'card-menu' : cardMenu,
	'card-order-details' : cardOrderDetails,
	'card-view-order' : cardViewOrder
  },
  methods: {
	hideMe: function(cardId) {
		var cid = cardId.cardId.toString();
		document.getElementById(cid).style.display = 'none';
	},
	status: function() {
		switch(this.orderStatus) {
			case "NEW ORDERS":
				return "NEW ORDER";
			case "IN PROGRESS":
				return "IN PROGRESS";
			case "WAITING FOR BUYER":
				return "DELIVERED";
			case "COMPLETED":
				counter++;
				if(counter < 3)
					return "COMPLETED";
				else
					return "CANCELLED";
			default:
				break;
		}
	},
  },
  computed: {
	indx: function() {
		return this.index;
	}
  }
  
}
</script>
<style>
.card {
	background-color: #fff;
	padding: 0.5rem 0rem;
	min-height: 30px;
	max-height: 325px;
	overflow: auto;
	border-radius: .6rem;
	font-size: 10px;
	display: grid;
}
</style>
