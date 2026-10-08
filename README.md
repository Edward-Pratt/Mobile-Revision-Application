# Mobile Revision App

A Kivy flashcard-style revision app backed by MySQL. Users register and log in, add and
delete questions, answer random questions to score points, and compare scores on a
leaderboard.

> An early project from 2022, kept for reference. It was one of my first apps using a GUI
> framework and a database.

## Features

- Login and registration screens
- Add, delete and answer revision questions
- Score tracking and a leaderboard
- Screens laid out in Kivy's `.kv` language (`mobile.kv`)

## Running

1. Install the dependencies:
   ```bash
   pip install kivy mysql-connector-python
   ```
2. Create a MySQL database with these tables:
   ```sql
   CREATE TABLE user (username VARCHAR(50) PRIMARY KEY, password VARCHAR(255), usersScore INT DEFAULT 0);
   CREATE TABLE questions (question VARCHAR(255) PRIMARY KEY, answer VARCHAR(255));
   ```
3. Copy `config.example.ini` to `config.ini` and fill in your database details.
4. Run `python main.py`.

## Known limitations

This is student code and isn't production-ready. Passwords are stored in plain text, and
some queries build SQL with string formatting instead of parameters.
