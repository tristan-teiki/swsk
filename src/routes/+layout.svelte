<script>
	import { goto } from '$app/navigation';
	import '../app.postcss';

	$: darkMode = false;
	$: showNav = false;
</script>

<nav class="{ darkMode ? 'dark-mode' : 'light-mode' } { showNav ? 'nav-visible' : '' }">
	<div class="nav-body">
		<div class="links">
			<a href="/services">Services</a>
			<a href="/testimonials">Testimonials</a>
			<a href="/blog">Blog</a>
			<a href="/academy">Academy</a>
		</div>
		<a id="get-in-touch" href="#">Get in Touch</a>
		<div class="sm-links">
			<a href="#">
				<img src="/images/sm-icons/lnkdn.svg" alt="LinkedIn Icon">
			</a>
			<a href="#">
				<img src="/images/sm-icons/inst.svg" alt="Instagram Icon">
			</a>
			<a href="#">
				<img src="/images/sm-icons/dsc.svg" alt="Discord Icon">
			</a>
			<a href="#">
				<img src="/images/sm-icons/tw.svg" alt="Twitter Icon">
			</a>
		</div>
	</div>
</nav>
<header
	class="{ darkMode ? 'dark-mode' : 'light-mode' }"
>
	<div class="container header">
		<a href="/" id="icon">
			<img src="/images/icon.svg" alt="Scalewhale Blue Icon">
		</a>
		<div class="controls">
			<div id="toggle"
				on:click={() => darkMode = !darkMode}
			>
				<img src="/images/sun.svg" alt="Sun Icon">
				<img src="/images/moon.svg" alt="Moon Icon">
				<div id="circle"
					style="transform: {darkMode ? 'translateX(0px)' : 'translateX(46px)'}"
				></div>
			</div>
			<div id="menu"
				class="{showNav ? "active" : ""}"
				on:click={() => showNav = !showNav}
			>
				<div class="line"></div>
				<div class="line"></div>
			</div>
		</div>
	</div>
</header>
<main 
	class="{ darkMode ? 'dark-mode' : 'light-mode' }"
>
	<slot />
</main>

<style lang=scss></style>