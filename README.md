Part 01: HTML - Neo Library
### part1 - the html
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
