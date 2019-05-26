---
title: "Create Table And Insert Data"
author: "TACT"
date: 2019-05-26
description: "-"
type: technical_note
draft: false
---

```python
import sqlalchemy
from sqlalchemy import create_engine
from sqlalchemy import Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker
```


```python
engine = create_engine('sqlite:///data.db', echo=True)
Base = declarative_base()
Session = sessionmaker(bind=engine)
session =  Session()
```


```python
class Country(Base):
    
    __tablename__ = 'country'
    
    id = Column(Integer, primary_key=True)
    name = Column(String)
    capital = Column(String)
    population = Column(Integer)
    
    def __init__(self, id, name, capital, population):
        self.id = id
        self.name = name
        self.capital = capital
        self.population = population
    
    def json(self):
        return {
            'id': self.id,
            'name': self.name,
            'capital': self.capital,
            'population': self.population
        }
```


```python
Base.metadata.create_all(engine)
```

    2019-05-26 19:23:42,957 INFO sqlalchemy.engine.base.Engine SELECT CAST('test plain returns' AS VARCHAR(60)) AS anon_1
    2019-05-26 19:23:42,959 INFO sqlalchemy.engine.base.Engine ()
    2019-05-26 19:23:42,962 INFO sqlalchemy.engine.base.Engine SELECT CAST('test unicode returns' AS VARCHAR(60)) AS anon_1
    2019-05-26 19:23:42,963 INFO sqlalchemy.engine.base.Engine ()
    2019-05-26 19:23:42,966 INFO sqlalchemy.engine.base.Engine PRAGMA table_info("country")
    2019-05-26 19:23:42,967 INFO sqlalchemy.engine.base.Engine ()
    2019-05-26 19:23:42,969 INFO sqlalchemy.engine.base.Engine 
    CREATE TABLE country (
    	id INTEGER NOT NULL, 
    	name VARCHAR, 
    	capital VARCHAR, 
    	population INTEGER, 
    	PRIMARY KEY (id)
    )
    
    
    2019-05-26 19:23:42,971 INFO sqlalchemy.engine.base.Engine ()
    2019-05-26 19:23:43,578 INFO sqlalchemy.engine.base.Engine COMMIT



```python
# insert some country row
item = Country(1, 'Chaina', 'Beijing', 138.64)
# add row in database
session.add(item) 
item = Country(2, 'India', 'New Delhi', 133.92)
# add row in database
session.add(item)
item = Country(3, 'France', 'Paris', 6.7)
# add row in database
session.add(item)
item = Country(4, 'United Kingdom', 'London', 6.6)
# add row in database
session.add(item)
item = Country(5, 'Germany', 'Berlin', 8.28)
# add row in database
session.add(item)

```


```python
# after insert row then want to commit
session.commit()
```

    2019-05-26 19:23:43,706 INFO sqlalchemy.engine.base.Engine BEGIN (implicit)
    2019-05-26 19:23:43,714 INFO sqlalchemy.engine.base.Engine INSERT INTO country (id, name, capital, population) VALUES (?, ?, ?, ?)
    2019-05-26 19:23:43,727 INFO sqlalchemy.engine.base.Engine ((1, 'Chaina', 'Beijing', 138.64), (2, 'India', 'New Delhi', 133.92), (3, 'France', 'Paris', 6.7), (4, 'United Kingdom', 'London', 6.6), (5, 'Germany', 'Berlin', 8.28))
    2019-05-26 19:23:43,742 INFO sqlalchemy.engine.base.Engine COMMIT



```python
# let see what data in country table
items = session.query(Country).all()
for item in items:
    print(item.json())

```

    2019-05-26 19:23:44,820 INFO sqlalchemy.engine.base.Engine BEGIN (implicit)
    2019-05-26 19:23:44,822 INFO sqlalchemy.engine.base.Engine SELECT country.id AS country_id, country.name AS country_name, country.capital AS country_capital, country.population AS country_population 
    FROM country
    2019-05-26 19:23:44,823 INFO sqlalchemy.engine.base.Engine ()
    {'id': 1, 'name': 'Chaina', 'capital': 'Beijing', 'population': 138.64}
    {'id': 2, 'name': 'India', 'capital': 'New Delhi', 'population': 133.92}
    {'id': 3, 'name': 'France', 'capital': 'Paris', 'population': 6.7}
    {'id': 4, 'name': 'United Kingdom', 'capital': 'London', 'population': 6.6}
    {'id': 5, 'name': 'Germany', 'capital': 'Berlin', 'population': 8.28}



```python
#
```


```python

```
