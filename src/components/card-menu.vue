<template>
<div class="menu-dots">
	<div class="card-menu"><a href="#submenu" @click="showSubMenu({cardId})" >...</a></div>
</div>
</template>

<script>
export default {
  name: 'card-menu',
  props: ['cardId'],
  methods: {
	showSubMenu : function(cardId) {
		this.$emit('hideCard', cardId);
	}
  }
}
</script>
<style>
.menu-dots{
	display: flow-root;
	padding: 0px 1rem 5px 1rem;
}
.card-menu {
	float: right;
	display: block;
	font-weight: bold;
}
</style>