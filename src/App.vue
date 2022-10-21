<template>
  <div class="app">
    <!--sidebar -->
    <Sidebar />
    <router-view />
  </div>
    
</template>


<script setup>
import Sidebar from './components/Sidebar.vue'
</script>


<style >
:root {
	 --primary: #4ade80;
	 --dark: #1e293b;
	 --grey: #64748b;
	 --dark-alt: #334155;
	 --light: #f1f5f9;
	 --sidebar-width: 300px;
}
 * {
	 margin: 0;
	 padding: 0;
	 box-sizing: border-box;
	 font-family: 'fira sans', sans-serif;
}
 body {
	 background: var(--light);
}
 button {
	 cursor: pointer;
	 appearance: none;
	 border: none;
	 outline: none;
	 background: none;
}
 .app {
	 display: flex;
}
 .app main {
	 flex: 1 1 0;
	 padding: 2rem;
}
 @media (max-width: 768px) {
	 .app main {
		 padding-left: 6rem;
	}
}
 
</style>