<svelte:head>
    <title>Contact</title>
</svelte:head>

<div class="wrapper">
    <main>
        <h1>Contact</h1>
    
        <a href="tel:2698232628">&#128222; (269) 823-2628</a>
    
        <form method="POST" action="https://formspree.io/f/mzbyrkkl">
            <div class="form-container">
                <div class="field-wrapper">
                    <div class="field">
                        <label for="name">Name</label>
                        <input type="text" name="name" id="name" placeholder="John Smith" required>
                    </div>
                    <div class="field">
                        <label for="email">Email</label>
                        <input type="email" name="email" id="email" placeholder="example@gmail.com" required>
                    </div>
                </div>
                <p>Message</p>
                <textarea name="message" id="message" placeholder="Message" rows="10" required></textarea>
                <input type="submit" value="Send" class="send" />
            </div>
        </form>
    </main>
</div>


<style>
.wrapper {
    display: flex;
    justify-content: center;
}

main {
    width: 75vw;
}

h1 {
    margin-bottom: 20px;
    padding-bottom: 5px;
    border-bottom: 1px solid var(--main-color);
}

a {
    font-size: 1.4rem;
    color: var(--black);
    text-decoration: none;
}

.form-container {
    margin-top: 10px;
    display: flex;
    flex-direction: column;
}

.field {
    margin-bottom: 10px;
}

label {
    font-size: 1.8rem;
}

input {
    margin-top: 5px;
    width: 100%;
    border-radius: 5px;
    border: 1px solid var(--black);
    line-height: 2rem;
}

p {
    font-size: 1.8rem;
}

textarea {
    margin-top: 5px;
    width: 100%;
    resize: none;
    font-family: inherit;
    border: 1px solid var(--black);
    border-radius: 5px;
    line-height: 1.2rem;
}

.send {
    color: var(--main-color);
    margin-top: 10px;
    width: auto;
    padding: 8px 15px;
    align-self: center;
    font-size: 1.6rem;
    border: 1px solid var(--main-color);
    border-radius: 50px;
    background: transparent;
}

.send:hover {
    background: var(--main-color);
    color: var(--white);
}

@media only screen and (min-width: 600px) {
    .field-wrapper {
        display: flex;
    }

    .field {
        width: 50%;
    }

    .field:first-of-type {
        margin-right: 10px;
    }
}

@media only screen and (min-width: 769px) {
    main {
        width: 50vw;
    }
}

@media only screen and (min-width: 1000px) {
    main {
        width: 35vw;
    }
}
</style>