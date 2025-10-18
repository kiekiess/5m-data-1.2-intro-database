# Assignment

## Brief

Create an ERD for each of the following case study question.

## Instructions

Paste the answer as DBML in the answer code section below each question.

### Question 1

Construct an ERD for a social media company whose database includes information about users, their followers, and the posts that they make. Users can follow multiple users and create multiple posts.

Each entity has the following attributes:

- User: id, username, email, created_at
- Post: id, title, body, user_id, status, created_at
- Follows: following_user_id, followed_user_id, created_at

Answer:

```dbml

```

### assignment 1.2 Q1

Table Users {
  id int [pk, increment]
  username varchar
  email varchar
  created_at timestamp
}

Table Posts {
  id int [pk, increment]
  title varchar
  body text
  user_id int
  status varchar
  created_at timestamp
}

Table Follows {
  following_user_id int
  followed_user_id int
  created_at timestamp
}

Ref: Posts.user_id > Users.id // many-to-one
Ref: Users.id < Follows.following_user_id // one-to-many
Ref: Users.id < Follows.followed_user_id // one-to-many


### Question 2

Construct an ERD for a company that sells books online. The company has a website where customers can browse available books and add them to their shopping carts. Each cart can contain multiple books.

There are 4 entities, think of what attributes each entity should have.

- Customer
- Book
- Cart
- CartItem

Answer:

```dbml

```

### assignment 1.2 Q1

Table Customer {
  id int [pk, increment]
  name varchar
  email varchar
  phone varchar
  address varchar
  created_at timestamp
}

Table Book {
  id int [pk, increment]
  title varchar
  description text
  author varchar
  book_type varchar
  publishing_co varchar
  publishing_year int
  isbn varchar
  stock_code varchar
  price dec
  }

Table Cart {
  id int [pk, increment]
  customer_id int
  status varchar   
  created_at timestamp     
}

Table Cart_Item {
  id int [pk, increment]
  cart_id int
  book_id int
  book_title varchar
  book_author varchar
  quantity int
  total_price dec
  created_at timestamp    
}


Ref: Cart.customer_id > Customer.id // many-to-one
Ref: Cart_Item.cart_id > Cart.id // many-to-one
Ref: Cart_Item.book_id > Book.id // many-to-one


## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
