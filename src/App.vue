<template>
  <main class="wrapper">
	<section class="navigation">
		<top-menu-header></top-menu-header>
	</section>
	<section class="main">
		<boards></boards>
	</section>
  </main>
</template>

<script>
import boards from './components/boards.vue';
import topMenuHeader from './components/top-menu-header.vue';

export default {
  name: 'App',
  components: {
    'top-menu-header' : topMenuHeader,
	boards
  }
}
</script>

<style>
h1 {
  font-family: serif, Arial;
}

h2, h3, h4, h5, h6, li {
  font-family: Arial, sans-serif;
}

p, a {
  font-family: Arial, sans-serif;
}

/* Generic styles */
html {
  scroll-behavior: smooth;
}
ol, ul {
	list-style: none;
	padding: 0px;
}
*{
	color: #a0a0a0;
}
a {
  background-color: white;
  text-decoration: none;
  color: #a0a0a0;
  text-align: center;
  display: inline-block;
  transition: all .3s;
  padding-top: 5px;
  padding-bottom: 5px;
}

a.n-current{ 
	color: green;
	border-bottom: green 3px solid;
}

a:hover {
  opacity: .6;
}
.wrapper {
	padding: 2px 4rem;
}

.drop-down-menu {
	position: absolute;
	display: none;
}
</style>