<template>
<div class="card-order-detail">
	<div class="order-img"><img :src="product()" /></div>
	<div class="order-details">
		<ul>
			<li><div :class="orderStatusClass"><span>{{orderStatus}}</span></div></li>
			<li>
				<div class="timer">
					<div class="timer-icon"><img src="assets/icons/timer.png" /></div> 
					<div class="timer-time">&nbsp;&nbsp;{{timerTimeText}}</div>
				</div>
			</li>
			<li>
				<div class="info">
					<div class="info-hrs">{{infoHrs}}</div>
					<div>{{showInfoHours}}</div>
					<div class="amt">{{infoAmt}}</div>
				</div>
			</li>
		</ul>
	</div>
</div>
</template>

<script>
export default {
  name: 'card-order-details',
  props: {
    timerTimeText: String, // default setting is '5 days left'
	infoHrs: String, // default setting is '20 hrs'
	showInfoHours: {
		type: String, // default text '&nbsp;&nbsp;|&nbsp;&nbsp;'. This can be set as boolean and then show/hide
		default: " | "
	},
	infoAmt: String, //default value '$320' in $
	productImage: String, //contains full path of the product image default is 'assets/products/F_Purse3_drop.jfif'
	productImagePath : {
		type: String,
		default: "./assets/products/"
	},
	orderStatus: String
  },
  methods: {
	product : function() {
		return this.productImagePath + this.productImage;
	},
  },
  created : function() {
	
  },
  computed: {
	orderStatusClass : function(){
		switch(this.orderStatus) {
			case "DELIVERED":
				return {'w4b-delivered' : true};
			case "NEW ORDER":
				return { 'new-order' : true };
			case "IN PROGRESS":
				return { 'in-progress' : true };
			case "COMPLETED":
				return { 'completed' : true };
			case "CANCELLED":
				return { 'cancelled' : true };
			default:
				return { [this.orderStatus.replace(" ", "-").toLowerStrinng()] : true };
		}
	}
  }
}
</script>
<style>
.card-order-detail{
	padding: 5px 1rem 20px 1rem;
}
.order-img {
	height: 60px;
	width: 60px;
	border: #F0F0F0 1px solid;
	border-radius: 5px;
	float: left;
}
.order-details > ul {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
	grid-template-rows: repeat(2, 24px);
}
.order-img > img {
	width: 60px;
}
.order-details > ul > li > div > span {
	padding: 4px 15px;
	border-radius: 15px;
	font-weight: bold;
	color: #875D3E;
}
.new-order > span {
	background-color: #FFECD0;
}
.in-progress > span{
	background-color: #D3DFFB;
}
.w4b-delivered > span{
	background-color: #FFD8EA;
}
.completed > span {
	background-color: #CAF4E1;
}
.cancelled > span {
	background-color: #E6E6E6;
}
.order-details .info .amt {
	font-weight: bold;
	color: #414141;
}
.order-details {
	display: grid;
	float: right;
	text-align: right;
	padding: 2px;
}
.order-details .timer .timer-icon > img {
	width: 10px;
}
.order-details .timer .timer-icon, .order-details .timer .timer-time, .order-details .info > div {
	display: inline;
}

</style>