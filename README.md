# flask-web-app-tutorial

This is a simple web application using Python Flask and MySQL database. This is a simple notes taking web application.

## What is Flask
Flask is a lightweight web application framework. It is designed to make getting started quick and easy, with the ability to scale up to complex applications.

## Install Flask
The easiest way to install Flask is to use PIP the official package-management tool.

``` pip install Flask ```
## Minimal Flask App
Open a terminal and install Flask (if not already installed) using PIP:

```  pip install Flask ``` 

Use your preferred editor to create a file called main.py with this content:

``` python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "<h1>Hello World!</h1>"

if __name__ == "__main__":
    app.run(host='0.0.0.0')
```
This will ensure that only the “main.py” will be run when the app starts.

### Start flask app

Save the file and start the app:

``` flask run ```

 * Serving Flask app "main"
 * Running on http://127.0.0.1:5000/
 
By visiting the app in the browser localhost:5000 we should see Hello World! message.

## Flask-SQLAlchemy
Flask-SQLAlchemy is an extension for Flask that adds support for SQLAlchemy to your application. It aims to simplify using SQLAlchemy with Flask by providing useful defaults and extra helpers that make it easier to accomplish common tasks.

### A Simple Example
```
from flask import Flask
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config["SQLALCHEMY_DATABASE_URI"] = "sqlite:///example.sqlite"
db = SQLAlchemy(app)

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String, unique=True, nullable=False)

with app.app_context():
    db.create_all()

    db.session.add(User(username="example"))
    db.session.commit()

    users = db.session.execute(db.select(User)).scalars()
```

## Demo link
https://drive.google.com/file/d/1_zPgxkMBR8Nj9WwL6Le70oRpfZo0AXIH/view?usp=share_link
