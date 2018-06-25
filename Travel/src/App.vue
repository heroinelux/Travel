<template>
  <div id="app">
    <main>
    	<keep-alive exclude="Detail">
    		<router-view></router-view>
    	</keep-alive>   
    </main>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
</style>
