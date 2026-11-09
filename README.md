# part 1 - the html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Neo Library</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
```
### nav bar
```html
    <nav class="navbar navbar-dark">
        <div class="container d-flex flex-wrap gap-3 justify-content-between">
            <a class="navbar-brand fw-bold" href="#home">📚 Neo Library</a>
            <div class="d-flex flex-wrap gap-3">
                <a class="nav-link-simple" href="#home">Home</a>
                <a class="nav-link-simple" href="#owned">Owned eBooks</a>
                <a class="nav-link-simple" href="#wishlist">Wishlist</a>
                <a class="nav-link-simple" href="#shop">Shop</a>
            </div>
        </div>
    </nav>
```
**What this does:** The links are able to go to sections on the same page using ids such as #owned and #wishlist.

### hero section
```html
    <section class="hero" id="home">
        <div class="container">
            <p class="hero-label mb-0">WELCOME TO YOUR READING CORNER</p>
            <h1 class="display-5 fw-bold">Find some books here to pass the time!</h1>
            <p class="lead mt-3">
                We're always looking to expand our collection but please enjoy the collection of books we have here!
            </p>
        </div>
    </section>
```
**What this does:** This is the arae with the big welcome heading and its animated background is controlled by css.

### search box
```html
        <div class="search-panel mb-4">
        <div class="row justify-content-center align-items-center g-3">
            <div class="col-md-7">
                <div class="search-box">
                    <span class="search-icon" aria-hidden="true">⌕</span>
                    <input type="search" class="form-control" id="searchBook"
                        placeholder="Search by book title or author..." aria-label="Search books">
                </div>
            </div>
            <div class="col-md-4">
                <select class="form-select" id="categoryFilter" aria-label="Filter books by category">
                    <option value="all">All Categories</option>
                    <option value="action">Action</option>
                    <option value="adventure">Adventure</option>
                    <option value="fantasy">Fantasy</option>
                    <option value="magic">Magic</option>
                </select>
            </div>
        </div>
        </div>
```
**What this does:** The input is where users type, the select element holds the category choices and their ids help JS find them.

### black clover
```html
        <div class="row g-4" id="ownedList">
            <div class="col-12 col-sm-6 col-lg-4 book-item" data-book="black-clover">
                <div class="card book-card h-100 shadow-sm">
                    <button class="star-button" onclick="toggleStar(this)" title="Favorite"
                        aria-label="Favorite Black Clover" aria-pressed="false">★</button>
                    <div class="cover-area">
                        <img src="https://is1-ssl.mzstatic.com/image/thumb/Publication49/v4/54/65/7e/54657eb9-bb85-b4b7-73ee-2efb0c99219f/9781421590776.jpg/1200x1200wy.jpg"
                            class="book-cover" alt="Black Clover">
                    </div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title">Black Clover</h5>
                        <p class="small text-secondary mb-2 book-category">Category: Fantasy / Magic</p>
                        <p class="text-muted book-author">Yuki Tabata</p>
                        <p class="price">$20.00</p>
                        <p class="book-summary">Asta dreams of becoming the Wizard King, even though he was born without magic.</p>
                        <div class="owned-actions">
                            <p class="text-success fw-bold mb-2">✓ Owned</p>
                            <button class="btn btn-read" onclick="readBook(this)">Read Book</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
```
**What this does:** This card involves a cover, a title, a author, a category, a price, summary and read book button.

### reader popup
```html
    <dialog id="readerDialog" class="reader-dialog">
        <div class="d-flex justify-content-between align-items-center gap-3">
            <h3 class="mb-0" id="readerTitle">Book Reader</h3>
            <button class="btn btn-outline-secondary" onclick="closeReader()" aria-label="Close reader">✕</button>
        </div>
        <p class="text-muted small mt-3">Demo reader: These are short project summaries, not pages from the actual eBook.</p>
        <p class="reader-page" id="readerText"></p>
        <div class="d-flex justify-content-between align-items-center gap-2">
            <button class="btn btn-outline-dark" id="previousPage" onclick="changePage(-1)">Previous</button>
            <span id="pageNumber">Page 1 of 2</span>
            <button class="btn btn-dark" id="nextPage" onclick="changePage(1)">Next</button>
        </div>
    </dialog>
```
**What this does:** The dialog element is the window that opens for the two pgae sample reader.

### footer
```html
    <footer class="text-white text-center py-4">
        <p class="mb-1">📚 Neo Library</p>
        <p class="mb-0">© 2026 Neo Library. Made for our group project.</p>
    </footer>
```
**What this does:** The footer is the bottom part of the website and shows the project credit.

# part 2 - the css

### page colors and font
```css
        body {
            background-color: #f8f6f2;
            color: #292824;
            font-family: Arial, sans-serif;
```
**What this does:** The body selector gives the whole website its cream background, dark text and Arial font.

### hero bg and txt
```css
        .hero {
            background-color: #181818;
            background-image: linear-gradient(rgba(0, 0, 0, 0.62), rgba(0, 0, 0, 0.62)), url("https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3aWlyNTcxOTJxMjV2dWpyODlvcXU4ZmE5ejJ0bWExaWppMDdoOXM2cSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/5k00E7cigvvqnBYDdP/giphy.gif");
            background-size: cover;
            background-position: center;
            padding: 74px 20px 80px;
            text-align: center;
            color: white;
        }
        .hero-label {
            color: #f0e4d4;
            font-size: 12px;
            font-weight: bold;
            letter-spacing: 2px;
        }
        .hero h1 { max-width: 760px; margin: 16px auto; line-height: 1.2; }
        .hero .lead { max-width: 650px; margin: auto; color: #f5f0e9; }
```
**What this does:** The GIF is the background image, and linear-gradient adds a black transparent overlay. Cover fills the banner, and center keeps the image in the middle.

### card shape and hover
```css
        .book-card {
            position: relative;
            display: flex;
            flex-direction: column;
            height: 100%;
            border: 1px solid #e7e2d9;
            border-radius: 16px;
            overflow: hidden;
            background-color: #fff;
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .book-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 28px rgba(0,0,0,0.10) !important;
```
**What this does:** Borders, rounded corners and shadows make the book cards neat. On hover, a card moves up a little.

### favorite star 
```css
        .star-button {
            position: absolute;
            right: 12px;
            top: 12px;
            z-index: 2;
            width: 37px;
            height: 37px;
            border: 1px solid #e7e2d9;
            border-radius: 50%;
            background-color: white;
            color: #a7a19a;
            font-size: 23px;
            line-height: 1;
            cursor: pointer;
        }
        .star-button.active { color: #efb625; }
        .star-button:hover { border-color: #efb625; }
```
**What this does:** The star is placed in the top-right corner of a card. The active class turns it yellow.

### buy and read buttons
```css
        .buy-actions, .owned-actions { margin-top: auto; padding-top: 12px; }
        .buy-actions .btn, .owned-actions .btn { border-radius: 9px; padding: 10px; font-size: 14px; }
        .buy-actions .btn { width: 100%; }
        .owned-actions .btn { width: 100%; }
        .btn-dark { background-color: #292929; border-color: #292929; }
        .btn-dark:hover { background-color: #41413c; }
        .btn-read { background: #326a50; border: 1px solid #326a50; color: white; }
        .btn-read:hover { background: #24513d; color: white; }
```
**What this does:** The buttons have matching shapes and sizes. The Read Book button is green.

### small screen adjustment
```css
        @media (max-width: 576px) {
            .hero { padding: 52px 16px; }
            .hero h1 { font-size: 30px; }
            .search-panel { padding: 15px; }
            .navbar-brand { font-size: 21px; }
        }
```
**What this does:** The media rule changes spacing and heading size on narrow screens.

# part 3 - bootstrap

### bootstrap link
```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
```
**What this does:** This link loads the Bootstrap stylesheet into our web page.

### nav layout
```html
    <nav class="navbar navbar-dark">
        <div class="container d-flex flex-wrap gap-3 justify-content-between">
            <a class="navbar-brand fw-bold" href="#home">📚 Neo Library</a>
            <div class="d-flex flex-wrap gap-3">
                <a class="nav-link-simple" href="#home">Home</a>
                <a class="nav-link-simple" href="#owned">Owned eBooks</a>
                <a class="nav-link-simple" href="#wishlist">Wishlist</a>
                <a class="nav-link-simple" href="#shop">Shop</a>
            </div>
        </div>
    </nav>
```
**What this does:** Container keeps content centered. d-flex arranges items in a row, and flex-wrap lets them move to another row on smaller screens.

### search grid
```html
        <div class="search-panel mb-4">
        <div class="row justify-content-center align-items-center g-3">
            <div class="col-md-7">
                <div class="search-box">
                    <span class="search-icon" aria-hidden="true">⌕</span>
                    <input type="search" class="form-control" id="searchBook"
                        placeholder="Search by book title or author..." aria-label="Search books">
                </div>
            </div>
            <div class="col-md-4">
                <select class="form-select" id="categoryFilter" aria-label="Filter books by category">
                    <option value="all">All Categories</option>
                    <option value="action">Action</option>
                    <option value="adventure">Adventure</option>
                    <option value="fantasy">Fantasy</option>
                    <option value="magic">Magic</option>
                </select>
            </div>
        </div>
        </div>
```
**What this does:** row creates a grid. col-md-7 and col-md-4 control the widths on medium screens. form-control and form-select style the inputs.

### responsive book column and card
```html
            <div class="col-12 col-sm-6 col-lg-4 book-item" data-book="black-clover">
                <div class="card book-card h-100 shadow-sm">
                    <button class="star-button" onclick="toggleStar(this)" title="Favorite"
                        aria-label="Favorite Black Clover" aria-pressed="false">★</button>
```
**What this does:** col-12 means one book across a small screen, col-sm-6 means two per row on small-and-up screens, and col-lg-4 means three per row on large screens.

### button styling
```html
                        <div class="buy-actions">
                            <button class="btn btn-dark mb-2" onclick="buyBook(this)">Pay $20 USD</button>
                            <button class="btn btn-outline-secondary wishlist-button" onclick="toggleWishlist(this)">Add to Wishlist</button>
                        </div>
                        <div class="owned-actions d-none">
                            <p class="text-success fw-bold mb-2">✓ Owned</p>
                            <button class="btn btn-read" onclick="readBook(this)">Read Book</button>
                        </div>
```
**What this does:** btn-dark gives the Pay button its dark style. btn-outline-secondary styles the Wishlist button. d-none hides the owned controls until purchase.

# part 4 - the javascript

JavaScript makes Neo Library interactive. It lets us search, favorite books, move books to the wishlist, simulate purchases, save choices and open the demo reader.

### search and filter books
```javascript
        document.getElementById("searchBook").addEventListener("input", searchBooks);
        document.getElementById("categoryFilter").addEventListener("change", searchBooks);

        function searchBooks() {
            const search = document.getElementById("searchBook").value.trim().toLowerCase();
            const category = document.getElementById("categoryFilter").value;
            let visibleCount = 0;

            document.querySelectorAll(".book-item").forEach(book => {
                const title = book.querySelector(".card-title").textContent.toLowerCase();
                const author = book.querySelector(".book-author").textContent.toLowerCase();
                const bookCategory = book.querySelector(".book-category").textContent.toLowerCase();

                const matchesSearch = (title + " " + author + " " + bookCategory).includes(search);
                const matchesCategory = category === "all" || bookCategory.includes(category);
                const match = matchesSearch && matchesCategory;

                book.classList.toggle("d-none", !match);
                if (match) visibleCount++;
            });

            document.getElementById("noResults").classList.toggle("d-none", visibleCount > 0);
        }
```
**What this does:** When a user types or changes the category, the function compares the search with book titles, authors and categories, then hides non-matches.

**What this does:** Clicking the star adds or removes the active CSS class, updates accessibility information and saves the result.

### moving books into the wishlist
```javascript
        function toggleWishlist(button) {
            const book = button.closest(".book-item");
            const wishlist = document.getElementById("wishlistList");
            const available = document.getElementById("availableList");

            if (book.parentElement.id === "availableList") {
                wishlist.appendChild(book);
                button.textContent = "Remove from Wishlist";
            } else {
                available.appendChild(book);
                button.textContent = "Add to Wishlist";
            }

            updateEmptyMessages();
            searchBooks();
            saveBooks();
        }
```
**What this does:** The function moves the chosen book card between the Available to Buy and Wishlist sections.

### simulated purchase
```javascript
        function buyBook(button) {
            const book = button.closest(".book-item");
            const title = book.querySelector(".card-title").textContent;
            const confirmed = confirm("Demo purchase: Add " + title + " to Owned eBooks? No real money will be charged.");

            if (confirmed) {
                document.getElementById("ownedList").appendChild(book);
                unlockBook(book);
                updateEmptyMessages();
                searchBooks();
                saveBooks();
            }
        }
```
**What this does:** A confirmation box appears. Confirming moves the book to Owned eBooks. This is not a real payment.

### unlock a book
```javascript
        function unlockBook(book) {
            book.querySelector(".locked-image").classList.remove("locked-image");
            book.querySelector(".lock-message").classList.add("d-none");
            book.querySelector(".buy-actions").classList.add("d-none");
            book.querySelector(".owned-actions").classList.remove("d-none");
        }
```
**What this does:** The locked label and payment controls are hidden, and the Read Book controls become visible.

### saving book state
```javascript
        function saveBooks() {
            const savedBooks = {};

            document.querySelectorAll(".book-item").forEach(book => {
                savedBooks[book.dataset.book] = {
                    section: book.parentElement.id,
                    favorite: book.querySelector(".star-button").classList.contains("active")
                };
            });

            localStorage.setItem("neoLibraryBooks", JSON.stringify(savedBooks));
        }
```
**What this does:** The browser stores each book's section and favorite star using localStorage.

### restore book state
```javascript
        function loadBooks() {
            const savedBooks = JSON.parse(localStorage.getItem("neoLibraryBooks")) || {};

            document.querySelectorAll(".book-item").forEach(book => {
                const saved = savedBooks[book.dataset.book];
                if (!saved) return;

                if (saved.section === "ownedList" || saved.section === "wishlistList" || saved.section === "availableList") {
                    document.getElementById(saved.section).appendChild(book);
                    if (saved.section === "ownedList" && book.querySelector(".locked-image")) {
                        unlockBook(book);
                    }
                    if (saved.section === "wishlistList") {
                        book.querySelector(".wishlist-button").textContent = "Remove from Wishlist";
                    }
                }

                if (saved.favorite) {
                    const star = book.querySelector(".star-button");
                    star.classList.add("active");
                    star.setAttribute("aria-pressed", "true");
                }
            });

            updateEmptyMessages();
            searchBooks();
        }
```
**What this does:** When the page opens, saved book sections and stars are restored from localStorage.

### open and turn reader pages
```javascript
        function readBook(button) {
            const book = button.closest(".book-item");
            currentPages = readerPages[book.dataset.book];
            currentPage = 0;
            document.getElementById("readerTitle").textContent = book.querySelector(".card-title").textContent;
            showPage();
            document.getElementById("readerDialog").showModal();
        }

        function showPage() {
            document.getElementById("readerText").textContent = currentPages[currentPage];
            document.getElementById("pageNumber").textContent = "Page " + (currentPage + 1) + " of " + currentPages.length;
            document.getElementById("previousPage").disabled = currentPage === 0;
            document.getElementById("nextPage").disabled = currentPage === currentPages.length - 1;
        }

        function changePage(amount) {
            currentPage += amount;
            showPage();
        }

        function closeReader() {
            document.getElementById("readerDialog").close();
        }

        loadBooks();
```
**What this does:** These functions open the dialog, display a short summary, and switch between page 1 and page 2.

