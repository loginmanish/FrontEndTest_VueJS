<template>
<div class="view-order">
	<div class="view-order-text"><span class="span-view-order"><div>View Order</div></span></div>
	<div class="view-order-images">
		<div class="order-user-chat"><img src="assets/icons/chat.png" /></div>
		<div class="order-user-thumbnail"><img :src="userImage()" /></div>
	</div>
</div>
</template>

<script>
export default {
  name: 'card-view-order',
  props: {
    userImageFile: String, //file name default can be 'assets/users/usr1.png'
	userImagePath: {
		type: String,
		default: "./assets/users/"
	},
  },
  methods: {
	userImage : function() {
		return this.userImagePath + this.userImageFile;
	},
  }
}
</script>
<style>
.order-user-chat > img {width: 30px;}
.order-user-thumbnail > img {width: 100%; height: 120%; object-fit: cover;}
.order-user-thumbnail{
	display: inline-block;
	width: 30px;
	height: 30px;
	border: 1px solid #F0F0F0;
	border-radius: 50%;
	overflow: hidden;
}
.view-order{
	padding: 10px 1rem;
	border-top: 1px solid #efefef;
}
.view-order-text, .view-order-images{
	display: inline;
}
.view-order-images {float:right;}
.order-user-chat, order-user-thumbnail {
	display: inline;
}
.view-order-text > div {height: 100%; v-align: middle;}
.span-view-order {
display: inline-table; 
vertical-align: middle; 
font-weight: bold; 
font-size: 12px; 
padding: 10px 0;
}
</style>