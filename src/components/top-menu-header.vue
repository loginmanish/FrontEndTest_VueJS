<template>
<h1>fiverr</h1><!-- Logo Image should be placed here-->
<ul>
	<li><a href="#Dashboard" >Dashboard</a></li>
	<li><a href="#Messages" >Messages</a></li>
	<li><a class="n-current" href="#Orders" >Orders</a></li>
	<li><a href="#Gigs" >Gigs</a></li>
	<li><a href="#Analytics" >Analytics</a></li>
	<li><a href="#Earnings" >Earnings</a></li>
</ul>
</template>
<script>
export default {
  name: 'top-menu-header',
  //TODO: Set props to dynamically put components above
}
</script>
<style>
.navigation {
	display: grid;
	grid-template-columns: 1fr 3fr;
	grid-template-rows: 100px;
	align-items: center;
}

.navigation > h1 {
  font-size: 3rem;
  padding-bottom: 1rem;
}

.navigation > ul {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(75px, 1fr));
	align-items: center;
	font-size: 1rem;
	padding-bottom: 1rem;
}
</style>