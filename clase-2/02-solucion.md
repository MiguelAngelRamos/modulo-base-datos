```sql

CREATE DATABASE biblioteca_db;

CREATE SCHEMA library;

CREATE TABLE library.genres (
    genre_id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    CONSTRAINT uq_genres_name UNIQUE(name)
);

CREATE TABLE library.authors (
    author_id       INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    author_code     VARCHAR(20) NOT NULL,
    full_name       VARCHAR(150) NOT NULL,
    nationality     VARCHAR(100),
    CONSTRAINT uq_authors_author_code UNIQUE(author_code)
);

CREATE TABLE library.books (
    book_id           INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    isbn              VARCHAR(20) NOT NULL,
    title             VARCHAR(200) NOT NULL,
    published_year    INT,
    genre_id          INT NOT NULL,
    author_id         INT NOT NULL,
    CONSTRAINT uq_books_isbn UNIQUE(isbn),
    CONSTRAINT chk_books_published_year CHECK(published_year > 1800),
    CONSTRAINT fk_books_genre FOREIGN KEY(genre_id) REFERENCES library.genres(genre_id),
    CONSTRAINT fk_books_author FOREIGN KEY(author_id ) REFERENCES library.authors(author_id )
);

CREATE TABLE library.members (
    member_id     INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    member_code   VARCHAR(20) NOT NULL, -- NO TE OLVIDES DEL UNIQUE
    full_name     VARCHAR(150) NOT NULL,
    email         VARCHAR(100) NOT NULL, -- No te olvides del unique
    joined_date   DATE         NOT NULL DEFAULT CURRENT_DATE,
    CONSTRAINT uq_members_member_code UNIQUE(member_code),
    CONSTRAINT uq_members_email UNIQUE(email)
);

CREATE TABLE library.loans (
    loan_id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    book_id INT NOT NULL,
    member_id INT NOT NULL,
    loan_date DATE NOT NULL DEFAULT CURRENT_DATE,
    due_date DATE NOT NULL, ---  No olvides del CHECK
    return_date DATE,
    CONSTRAINT chk_loans_due_date CHECK(due_date > loan_date),
    CONSTRAINT chk_loans_return_date CHECK(return_date IS NULL OR return_date >= loan_date),
    CONSTRAINT fk_loans_book_id FOREIGN KEY(book_id) REFERENCES library.books(book_id),
    CONSTRAINT fk_loans_member_id FOREIGN KEY(member_id) REFERENCES library.members(member_id)

);




```
