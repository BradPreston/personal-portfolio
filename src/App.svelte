<svelte:head>
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400&display=swap" rel="stylesheet">
</svelte:head>

<script>
	import { activeNavLink } from './stores';
	import router from 'page';
	import { onDestroy } from 'svelte';
	// Routes
	import Home from './Home.svelte';
	import About from './About.svelte';
	import Portfolio from './Portfolio.svelte';
	import Blog from './Blog.svelte';
	import Contact from './Contact.svelte';
	import NotFound from './NotFound.svelte';
	import Footer from './components/Footer.svelte';
  
	// Route Config
	router('/', () => page = Home);
	router('/about', () => page = About);
	router('/portfolio', () => page = Portfolio);
	router('/blog', () => page = Blog);
	router('/contact', () => page = Contact);
	router('/*', () => page = NotFound);
  
	let page;
	let currentPage;

	const unsubscribe = activeNavLink.subscribe(active => {
		currentPage = active;
	});

	onDestroy(unsubscribe);

	
	const toggleNav = () => {
		let navLinks = document.getElementById('nav-links');

		if (navLinks.style.display !== 'flex') {
			navLinks.style.display = 'flex';
		} else {
			navLinks.style.display = 'none';
		}

		navLinks.addEventListener('click', () => {
			navLinks.style.display = 'none';
		});
	}

	// Start Router
	router.start();
</script>
  
<nav>
	<div id="nav-links">
		<a href='/'
			class={$activeNavLink === 'home' ? 'active' : ''}
			on:click={() => activeNavLink.set('home')}>
			Home
		</a>
		<a href='/about'
			class={$activeNavLink === 'about' ? 'active' : ''}
			on:click={() => activeNavLink.set('about')}>
			About
		</a>
		<a href='/portfolio'
			class={$activeNavLink === 'portfolio' ? 'active' : ''}
			on:click={() => activeNavLink.set('portfolio')}>
			Portfolio
		</a>
		<a href='/blog'
			class={$activeNavLink === 'blog' ? 'active' : ''}
			on:click={() => activeNavLink.set('blog')}>
			Blog
		</a>
		<a href='/contact'
			class={$activeNavLink === 'contact' ? 'active' : ''}
			on:click={() => activeNavLink.set('contact')}>
			Contact
		</a>
	</div>

	<button on:click={toggleNav}>
		<span></span>
		<span></span>
		<span></span>
	</button>
</nav>
  
<svelte:component this={page} />
  
<Footer />

<style>

:global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:global(:root) {
    --main-color: #ff9934;
    --main-light: #ffa64e;
    --main-lighter: #ffb76f;
    --main-dark: #ff8b1a;
    --main-darker: #ff7f00;
    --black: #333;
    --white: #fff;
    font-size: 10px;
}

:global(body) {
    font-size: 1.6rem;
    font-family: Roboto, 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: var(--black);
    margin: 0 auto;
}

:global(h1){
    color: var(--main-color);
    font-weight: 100;
    font-size: 3rem;
}

:global(h2) {
    font-weight: 100;
    font-size: 1.6rem;
}

:global(.wrapper) {
    height: calc(100vh - 90px);
    width: 100vw;
    margin-top: 50px;
}

@media only screen and (min-width: 481px) {
    :global(h1) {
        font-size: 4rem;
    }

    :global(h2) {
        font-size: 2rem;
    }
}

@media only screen and (min-width: 769px) {
    /* :global(h1) {
        font-size: 6rem;
    } */

    :global(h2) {
        font-size: 2rem;
    }
}



nav {
	width: 100vw;
	height: 50px;
	position: fixed;
	top: 0;
	display: flex;
	justify-content: flex-end;
	align-items: center;
	border-bottom: 1px solid var(--main-color);
	background: var(--white);
	z-index: 1000;
}

button {
	height: 20px;
	width: 30px;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	border: none;
	margin-right: 20px;
}

span {
	width: 100%;
	height: 3px;
	background: var(--black);
	border-radius: 100px;
}

#nav-links {
	display: none;
	flex-direction: column;
	align-items: flex-end;
	position: absolute;
	z-index: 1000000;
	top: 50px;
	background: rgba(255, 255, 255, .9);
	width: 100vw;
	height: 100vh;
	padding-right: 20px;
}

a {
	font-size: 3rem;
	color: var(--black);
	text-decoration: none;
	text-transform: capitalize;
	margin: 10px 0;
	transition: .25s ease;
	font-weight: 300;
}

a:hover {
	color: var(--main-color);
}

a:first-of-type {
	margin-top: 10px;
}

.active {
	color: var(--main-color);
}

@media only screen and (min-width: 768px) {
	button {
		display: none;
	}

	a {
		padding: 0 10px;
		border-bottom: 3px solid transparent;
		font-size: 1.8rem;
	}

	a:hover {
		border-bottom: 3px solid var(--main-color);
	}

	#nav-links {
		display: flex !important;
		flex-direction: row;
		height: 50px;
		top: 0;
		align-items: center;
		justify-content: center;
		padding-right: 0;
		background: transparent;
	}

	nav {
		padding: 0 10px;
		line-height: 45px;
		font-size: 1.8rem;
	}

	.active {
		border-bottom: 3px solid var(--main-color);
	}
} 
</style>