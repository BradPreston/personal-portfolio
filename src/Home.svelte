<script>
    import { activeNavLink } from './stores.js';
</script>

<svelte:head>
    <title>Home</title>
</svelte:head>

<div class="wrapper">
    <main class="no-webp webp">
        <section>
            <h1>My name is Brad Preston</h1>
            <h2>I am a web developer from Kalamazoo, MI</h2>
            <a href="/about" on:click={() => activeNavLink.set('about')}>My story<span class="arrow">&#8594;</span></a>
        </section>
    </main>
</div>


<style>

main {
    width: 100%;
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
}

.no-webp {
    background: linear-gradient(rgba(0, 0, 0, .75), rgba(0, 0, 0, .75)), url('/images/desk.jpeg');
    background-position: 100%;
    background-size: cover;
    background-attachment: fixed;
}

.webp {
    background: linear-gradient(rgba(0, 0, 0, .75), rgba(0, 0, 0, .75)), url('/images/desk.webp');
    background-position: 100%;
    background-size: cover;
    background-attachment: fixed;

}

h2 {
    color: #fff;
    margin-bottom: 20px;            
}

a {
    color: white;
    border-bottom: 1px solid var(--main-color);
    text-decoration: none;
    padding-bottom: 5px;
    font-weight: 300;
    font-size: 1.6rem;
    display: flex;
    align-items: center;
    width: 84px;
    transition: .25s ease;
}

a:hover {
    color: var(--main-color);
}

.arrow {
    padding-left: 5px;
    border-bottom: 1px solid transparent;
}

a:hover > .arrow {
    animation-name: slidingArrow;
    animation-duration: .75s;
    animation-iteration-count: infinite;
}

@keyframes slidingArrow {
    0% {
        padding-left: 5px;
    }
    50% {
        padding-left: 7px;
    }
    100% {
        padding-left: 5px;
    }
}

@media only sreen and (min-width: 769px) {
    a {
        font-size: 2rem;
        width: 103px;
    }
}
</style>