# SellBook

SellBook is a marketplace for books, with the objective of giving a second chance to books that would stay unread and offering a fair price to the interested readers.


## Content

The project consists for the moment of a HTML document (index.html), a CSS document (styles.css) and a JavaScript document (left-menu.js). For the second task a second HTML document (sell.html), CSS (sell.css) and JavaScript (sell-list.js) were added. Lastly, for the third task a third HTML document (buy.html), CSS (buy.css) and JavaScript (import-products.js) were added.


## Important elements of the Task 1

In the index.html there are some elements that take the spotlight: mainly the LOG IN button (using a simple but satisfing animation), the side menu and the footer. I decided the colors (mainly black/dark and pink) to create something appealing that will attract the users.

### Log In button code:

```css
.button-slide {
    margin-top: 0.5em;
    margin-left: 22em;
    color: #FFF;
    border: 1px solid rgb(216, 2, 134);
    border-radius: 0px;
    padding: 9px 18px;
    display: inline-block;
    font-family: "Lucida Console", Monaco, monospace;
    font-size: 12px;
    letter-spacing: 1px;
    cursor: pointer;
    box-shadow: inset 0 0 0 0 #D80286;
    -webkit-transition: ease-out 0.4s;
    -moz-transition: ease-out 0.4s;
    transition: ease-out 0.4s;
}
```

### Side Menu code:
```css
#side-menu {
    position: fixed;
    width: 50px;
    height: 100%;
    background-color: #151725;
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

## Important Elements of the Task 2

In the sell.html document there are some fields for the BootStrap schema, aswell as the necessary for the different fields of the formulary. This is accompanied by the respective CSS document for the styles, but most importantly, by the JavaScript document to validate the data in the BootStrap form. 

### One of the fields of the form:
```html
<div class="form-floating mb3">
     <select class="form-select" id="category" name="sellist">
         <option>Novel</option>
         <option>Manga</option>
         <option>Graphic Novel</option>
         <option>Comic</option>
         <option>Other</option>
     </select>
     <label for="category" class="form-label">Category(select one):</label>
     <p id="category-error">*Category cannot be empty</p>
</div>
```

### The last section of the validation, for generating the data introduced:
```javascript
function showBooks(){
    const SELL_LIST=document.getElementById("sell-list");

    let allBooks="";
    for (let i = 0; i < books.length; i++) {
        allBooks+=`<li>Title: ${books[i].title} <br>Category: ${books[i].category} <br>Price: ${books[i].price}€<br><button onclick="deleteBook(${i})">Remove</button></li>`;

    }

    SELL_LIST.innerHTML=allBooks;
}

function deleteBook(bookId){
    books.splice(bookId, 1);
    showBooks();
}
```

## Important Elements of the Task 3

The objective of this task was to integrate localStorage code to the page, using the form included in the last task to save data and show it in the buy.html page. To make this possible the VisualStudio extension LiveServer is necessary, as the localStorage is shared bewteen different pages from the same domain.

### The container from the buy.html page that stores the data:
```html
</div>
    <div id="buyable">

    </div>
</div>
```

### The section of the buy.css document that gives format to the stored data:
```css
.sale-list {
    width: 100vw;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    flex-wrap: wrap;
}

#buyable {
    width: 100vw;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    flex-wrap: wrap;
}

.item {
    margin-top: 1em;
    border: 3px solid #D80286;
    padding: 1em;
    width: 50vw;
    color: white;
    font-family: "Lucida Console", Monaco, monospace;
    font-size: small;
    display: inline-block;
}
```

### The code used to store the data from the sell.html form
```javascript
const booksInStringFormat = JSON.stringify(books);
window.localStorage.setItem("books", booksInStringFormat);
showBooks();
```

### The code used to get the data and use it in the buy.html page
```javascript
let products = [

];

function initialize() {
    const booksInStringFormat = window.localStorage.getItem("books");
    let books = JSON.parse(booksInStringFormat);
    const BUYABLE = document.getElementById("buyable");
    let products = "";
    for (let i = 0; i < books.length; i++) {
        products +=
        `
        <div class="product">
            <ul class="book">
                <li class="item"><span>${books[i].title}, ${books[i].category} by ${books[i].author} for ${books[i].price}€</span>
                <br>
                    <input type="number" id="quantity" name="quantity" min="0" max="5">
                    <br>
                    <span class="add-to-chart slide-right">ADD TO CART</span>
                    </li>
            </ul>
        </div>
        
        `
    }

    BUYABLE.innerHTML = products;
}

initialize();
```

## Gratitudes:

I have used the next [web page](https://dribbble.com/shots/22892019-DeFi-Coin-Web-3-0-Platform) as inspiration for the design. I have also been helped by my classmate Alejandro Abreu in the ":hover" function or some design choices. For the last task I have received much help from Tiburcio, and I could not have finished the task without this help.

## Authors

- Víctor Gómez Fernández
