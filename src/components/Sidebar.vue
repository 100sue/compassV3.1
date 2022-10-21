<template>
  <aside :class="`${is_expanded && 'is-expanded'}`">

      <div class="logo">
          <img src="../assets/compass.png" alt="logo du site">
      </div>

      <div class="menu-toggle-wrap">
          <button class="menu-toggle" @click="ToggleMenu">
              <span class="material-icons">keyboard_double_arrow_right</span>
          </button>
      </div>

      <h3>Menu</h3>
      <div class="menu">
          <router-link class="button" to="/">
              <span class="material-icons">home</span>
              <span class="text">Home</span>
          </router-link>
          <router-link class="button" to="/about">
              <span class="material-icons">visibility</span>
              <span class="text">About</span>
          </router-link>
          <router-link class="button" to="/team">
              <span class="material-icons">group</span>
              <span class="text">Team</span>
          </router-link>
          <router-link class="button" to="/contact">
              <span class="material-icons">email</span>
              <span class="text">Contact</span>
          </router-link>
      </div>

      <div class="flex"></div>
      <div class="menu">
          <router-link class="button" to="/settings">
              <span class="material-icons">settings</span>
              <span class="text">Settings</span>
          </router-link>
      </div>


  </aside>

</template>

<script setup>
import { ref } from 'vue'

const is_expanded = ref(localStorage.getItem("is_expanded") === "true")

const ToggleMenu = () => {
  is_expanded.value = !is_expanded.value
  localStorage.setItem("is_expanded", is_expanded.value)

}
</script>


<style scoped>
aside {
	 display: flex;
	 flex-direction: column;
	 width: calc(2rem + 32px);
	 min-height: 100vh;
	 overflow: hidden;
	 padding: 1rem;
	 background-color: var(--dark);
	 color: var(--light);
	 transition: 0.2s ease-out;
}
 aside .flex {
	 flex: 1 1 0;
}
 .logo {
	 margin-bottom: 1rem;
}
 aside .logo img {
	 width: 2rem;
}
 aside .menu-toggle-wrap {
	 display: flex;
	 justify-content: center;
	 margin-bottom: 1rem;
	 position: relative;
	 top: 0;
	 transition: 0.2s ease-out;
}
 aside .menu-toggle-wrap .menu-toggle {
	 transition: 0.2s ease-out;
}
 aside .menu-toggle-wrap .menu-toggle .material-icons {
	 font-size: 2rem;
	 color: var(--light);
}
 aside .menu-toggle-wrap .menu-toggle:hover .material-icons {
	 color: var(--primary);
	 transform: translateX(0.5rem);
}
 aside h3, aside .button .text {
	 opacity: 0;
	 transition: 0.3s ease-out;
}
 aside h3 {
	 color: var(--grey);
	 font-size: 0.875rem;
	 margin-bottom: 0.5rem;
	 text-transform: uppercase;
}
 aside .menu {
	 margin: 0 -1rem;
}
 aside .menu .button {
	 display: flex;
	 align-items: center;
	 text-decoration: none;
	 padding: 0.5rem 1rem;
	 transition: 0.2s ease-out;
}
 aside .menu .button .material-icons {
	 font-size: 2rem;
	 color: var(--light);
	 transition: 0.2s ease-out;
}
 aside .menu .button .text {
	 color: var(--light);
	 transition: 0.2s ease-out;
}
 aside .menu .button:hover, aside .menu .button.router-link-exact-active {
	 background-color: var(--dark-alt);
}
 aside .menu .button:hover .material-icons, aside .menu .button.router-link-exact-active .material-icons, aside .menu .button:hover .text, aside .menu .button.router-link-exact-active .text {
	 color: var(--primary);
}
 aside .menu .button.router-link-exact-active {
	 border-right: 5px solid var(--primary);
}
 aside.is-expanded {
	 width: var(--sidebar-width);
}
 aside.is-expanded .menu-toggle-wrap {
	 top: -3rem;
}
 aside.is-expanded .menu-toggle-wrap .menu-toggle {
	 transform: rotate(-180deg);
}
 aside.is-expanded h3, aside.is-expanded .button .text {
	 opacity: 1;
}
 aside.is-expanded .button .material-icons {
	 margin-right: 1rem;
}
 @media (max-width: 768px) {
	 aside {
		 position: fixed;
		 z-index: 99;
	}
}
 
</style>
