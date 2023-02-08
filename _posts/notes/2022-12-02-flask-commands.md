---
title: "Flask Commands (Way of Django)"
date: 2022-12-02
draft: false
tags: ["python"]
categories: [programming]
---

#### Declaring models with SQLAlchemy

```python
class Person(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(50), nullable=False)
    addresses = db.relationship('Address', backref='person', lazy=True)

class Address(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    email = db.Column(db.String(120), nullable=False)
    person_id = db.Column(db.Integer, db.ForeignKey('person.id'),
        nullable=False)

```

#### Commands to get ready and run local environment
```shell
# Run app in debug mode:
$ flask --app main --debug run

# Start migrations
$ flask --app main db init

# make migrations
$ flask --app main db migrate

# migrate changes
$ flask --app main db upgrade


# Run debug server
$ flask --app main --debug run


# Run shell
$ flask --app main shell


# Deleting from a shell:

>>> from models import db, MLProject
>>> MLProject.query.delete()
>>> db.session.commit()

```

