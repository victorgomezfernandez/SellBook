# SellBook

SellBook is a marketplace for books, with the objective of giving a second chance to books that would stay unread and offering a fair price to the interested readers.


## Content

The project consists for the moment of a HTML document (index.html), a CSS document (styles.css) and a JavaScript document (left-menu.js). For the second task a second HTML document (sell.html), CSS (sell.css) and JavaScript (sell-list.js) were added.


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

## Gratitudes:

I have used the next [web page](https://dribbble.com/shots/22892019-DeFi-Coin-Web-3-0-Platform) as inspiration for the design. I have also been helped by my classmate Alejandro Abreu in the ":hover" function or some design choices (for example).

## Authors

- Víctor Gómez Fernández
