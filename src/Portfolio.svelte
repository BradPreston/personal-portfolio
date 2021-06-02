<svelte:head>
    <title>Portfolio</title>
</svelte:head>

<script>
    import Card from './components/Portfolio_Card.svelte';
</script>

<div class="wrapper">
    <main>
        <h1>Portfolio</h1>
        <section>
            <Card
                title={"Aaron's Music Service"}
                link={"http://www.aaronsmusicservice.com"}
                image={"images/build.webp"}
                alt={"Aaron's Music Service"}
            />

            <Card
                title={"Photos with Paul"}
                link={"http://www.photoswithpaul.com"}
                image={"images/bird.webp"}
                alt={"Photos With Paul"}
            />
        </section>
    </main>
</div>

<style>
main {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 75vw;
    margin: 0 auto;
    padding-bottom: 50px;
}

h1 {
    margin-bottom: 20px;
}

section {
    display: flex;
    flex-direction: column;
    width: 100%;
    align-items: center;
}

@media only screen and (min-width: 769px) {
    section {
        flex-direction: row;
        justify-content: center;
    }
}
</style>