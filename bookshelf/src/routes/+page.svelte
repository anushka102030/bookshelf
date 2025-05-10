<script>
    import { onMount } from "svelte";
    /**
	 * @type {{ title: any; review: any; image?: string; } | null}
	 */
    let selectedBook = null;
    let modalVisible = false;
    let bookPosition = { top: 0, left: 0, width: 0, height: 0 };

    const books = [
        {
            title: "Remarkably Bright Creatures",
            image: "https://m.media-amazon.com/images/I/81lm4oD9ONL._UF1000,1000_QL80_.jpg",
            review: "A heartwarming story about a friendship between a woman and an octopus."
        },
        {
            title: "Another Book Title",
            image: "https://via.placeholder.com/150",
            review: "This is a placeholder review for another book."
        }
    ];

    /**
	 * @param {{ title: any; review: any; image?: string; } | null} book
	 * @param {{ target: { getBoundingClientRect: () => any; }; } | any} [event]
	 */
    function openReview(book, event) {
        const rect = event.currentTarget.getBoundingClientRect();
        bookPosition = {
            top: rect.top,
            left: rect.left,
            width: rect.width,
            height: rect.height
        };
        selectedBook = book;

        // Add a slight delay to trigger the transition
        setTimeout(() => {
            modalVisible = true;
        }, 10); // 10ms delay
    }

    function closeReview() {
        modalVisible = false;
        setTimeout(() => {
            selectedBook = null;
        }, 300); // Wait for the animation to finish
    }
</script>

<h1>OKBye Bookshelf</h1>
<p>Visit <a href="https://www.youtube.com/watch?v=LyvyfhYcwnA&list=PL_lg81dMuYpLpRXg6TtddYA3N47es8ZGP&pp=0gcJCV8EOCosWNin">OkBye Book Club</a> for detailed reviews</p>
<p> Tejas is the biggest butt on planet earth</p>

<!-- 
<div class="bookshelf">
    {#each books as book}
        <button  class="book" on:click={(event) => openReview(book, event)}>
            <img src={book.image} alt={book.title}>
            <p>{book.title}</p>
        </button>
    {/each}
</div>

{#if selectedBook}
    <div class="modal">
        <div class="modal-content">
            <button class="close" on:click={closeReview}>&times;</button>
            <div class="modal-v">
                <img src={selectedBook.image} alt={selectedBook.title}>
                <div class="modal-text">
                    <h2>{selectedBook.title}</h2>
                    <p>{selectedBook.review}</p>
                </div>
            </div>
        </div>
    </div>
{/if} -->

<div class="bookshelf">
    {#each books as book}
        <button class="book" on:click={(event) => openReview(book, event)}>
            {#if !(book.title === selectedBook?.title)}
                <img src={book.image} alt={book.title}>
            {/if}
            <p>{book.title}</p>
        </button>
    {/each}
</div>

{#if selectedBook}
    <div class="modal {modalVisible ? 'visible' : ''}">
        <div
            class="modal-image"
            style="
                top: {bookPosition.top}px;
                left: {bookPosition.left}px;
                width: {bookPosition.width}px;
                height: {bookPosition.height}px;
                background-image: url({selectedBook.image});
            "
        ></div>
        <div class="modal-content">
            <button class="close" on:click={closeReview}>&times;</button>
            <div class="modal-text">
                <h2>{selectedBook.title}</h2>
                <p>{selectedBook.review}</p>
            </div>
        </div>
    </div>
{/if}

<style>
    h1 {
        display: flex;
        justify-content: center;
        font-size: xx-large;
        align-items: center;
        font-family: 'Courier New', monospace;
        font-weight: bolder;
    }

    .bookshelf {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
        gap: 12rem;
        padding: 5rem;
    }

    .book {
        text-align: center;
        border: 1px solid #ddd;
        padding: 10px;
        border-radius: 8px;
        background-color: #f9f9f9;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        height: 35rem;
        width: 20rem;
        cursor: pointer
    }

    .book:hover {
        transform: scale(1.05); /* Add hover effect for better feedback */
    }

    .book img {
        width: 100%;
        height: auto;
        border-radius: 4px;
    }

    .book p {
        margin-top: 10px;
        font-size: 16px;
        font-weight: bold;
        color: #333;
    }

    /* Modal styles */
    .modal {
        position: relative;
        bottom: 40em;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.103);
        display:flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
        opacity: 0;
        pointer-events: none;
        transition: opacity 0.3s ease;
    }

    .modal.visible {
        opacity: 1;
        pointer-events: auto;
        transition-duration: 1s;
    }

    .modal-image {
        position: fixed;
        background-size: cover;
        background-position: center;
        border-radius: 8px;
        transition-duration: 2s;
    }

    .modal.visible .modal-image {
        position: fixed;
        transform: translate(30%, 0%);
        transition-duration: 2s;
    }

    .modal-content {
        background-color: #fff;
        padding: 20px;
        border-radius: 8px;
        width: 80%;
        max-width: 600px;
        text-align: left;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        z-index: 1;
    }

    .modal-text {
        flex: 1;
    }

    .modal-text h2 {
        margin: 0;
        font-size: 1.5rem;
        font-weight: bold;
    }

    .modal-text p {
        margin-top: 10px;
        font-size: 1rem;
        color: #555;
    }

    .close {
        position: absolute;
        top: 10px;
        right: 20px;
        font-size: 24px;
        background: none;
        border: none;
        cursor: pointer;
    }
    
</style>