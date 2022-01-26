## Adding Programmabilty to SQL with Templates using Python and `jinja2`    

### Accessing Materials

For the pre-populated notebook, see: [jinja_sql_demo.ipynb](jinja_sql_demo.ipynb)

Link to interactive demo via notebook binder: 
* https://mybinder.org/v2/gh/paulzuradzki/jinja_sql_demo/HEAD
* Your first time loading the notebook may take a minute as the "binder" is setting up an environment with jinja2, so you don't have to install anything locally
* Do NOT paste any sensitive data in this binder environment. 
  * A Jupyter Lab session will be launched, but it is on a separate machine for convenience and learning purposes only (note the URL does not say `localhost`).
  * You can still follow the examples and experiment with templating in the supplied environment. For real or sensitive data, you should set up an environment locally.


### Introduction
This notebook is a brief tutorial and demo of how to programmatically generate SQL.

```
"Languages shape the way we think and determines what we can think about." 
~ Benjamin Wharf, American linguist
```
```
Keep it D.R.Y. Don't Repeat Yourself.
```

**Why use templating over SQL built-in functionality like SQL variables, stored procedures, and loops?**
While you can use many programming features in SQL -- variables, loops, conditionals -- it doesn't mean that you always should. In SQL, tables and rows are the main abstractions. If you want to loop through a list of elements or handle more complicated data structures, SQL might get in the way. Additionally, say, you have several tables following a convention of table_<year> (table_2020, table_2021, etc). In SQL, to parameterize the year, you likely have to construct strings dynamically. This sort of programming and string manipulation becomes much more tedious than necessary compared to a procedural programming language (Python, Python+templating language).

**Why not to use templating?**
If all you need is a handful or less of parameterization (variables) or loops, SQL stored procedures and SQL loops might be all that you want without the added glue scripting from Python. In analytics, SQL is often the primary language so depending on your collaborators' background, the jump from basic SQL to intermediate/advanced SQL might be smaller than the jump to Python or another procedural programming langugage.
<br>Assuming a little Python familiarity, I'd argue that even for basic programmability, SQL with templates is easier to maintain and read.

### Contents
* Variables
* Looping
* Conditionals
* Special loop variables
* Note on SQL injection for web applications

### Resources
* https://jinja.palletsprojects.com/en/3.0.x/templates
* https://realpython.com/primer-on-jinja-templating
