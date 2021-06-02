<script>
    export let image;
    export let alt;
    export let title;
    export let link;
</script>

<div class="card">
    <img class="image" src={image} alt={alt} />
    <div class="card-content">
        <h3>{title}</h3>
        <a href={link} target="_blank">Visit site <span class="arrow">&#8594;</span></a>
    </div>
</div>

<style>
.card {
    height: 250px;
    width: 250px;
    margin-bottom: 40px;
    position: relative;
}

.card:hover > .card-content {
    background: rgba(0, 0, 0, .7);
}

.image {
    width: 100%;
    height: 100%;
    border-radius: 400px;
    object-fit: cover;
    background: var(--main-lighter);
}

.card-content {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, .5);
    border-radius: 400px;
    color: var(--white);
    transition: .25s ease;
}

h3 {
    margin-bottom: 10px;
}

a {
    color: white;
    border-bottom: 1px solid var(--main-color);
    text-decoration: none;
    padding-bottom: 5px;
    font-weight: 300;
    font-size: 1.6rem;
    display: flex;
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
        padding-left: 5px;
        border-bottom: 1px solid transparent;
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

@media only screen and (min-width: 481px) and (max-width: 768px) {
    .card {
        height: 300px;
        width: 300px;
    }
}

@media only screen and (min-width: 769px) {
    .card {
        margin: 0 20px;
    }

    a {
        font-size: 2rem;
        width: 103px;
    }
}

@media only screen and (min-width: 900px) {
    .card {
        height: 300px;
        width: 300px;
    }
}

@media only screen and (min-width: 1200px) {
    .card {
        width: 400px;
        height: 400px;
    }
}

</style>