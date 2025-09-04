## Inserting
- Same as postgres - ```INSERT INTO mydb VALUES (column based values)```
- Note - for multiple values, leverage lists. Say you have name, age and fruit fields. Do:
  - ```
    data = [
      (a, 1, mango),
      (b, 2, orange),
      (c, 3, guava)
    ]

    curs.executemany("INSERT INTO  mydb (?, ?, ?)", data)
    ```
- Note we use executemany() for instead of execute() and use placeholders (?, ?, ?)

 ## Fetching
- To fetch first execute the select query, say: ```curs.execute("SELECT * FROM mydb")```
- Now we can run:
  - ```curs.fetchone()``` to fetch the next available row as a tuple and returns none when result set is exahausted
  - ```curs.fetchmany([number goes here])``` to fetch an entered number of rows, remember the cursor goes ahead by the number of rows fetched
  - ```curs.fetchall()``` to get all available rows from current cursor position and empty set if the cursor is at the end
- Note: If you want all rows, just use ```fetchall()```, using fetchone() and then fetchall() will return rows from 1-end instead of 0-end
- Finally to to actually get the out put, you have to print the result instead of just running the fetch function, so like ```print(curs.fetchone())``` and same for the other two
- Note: Since the outputs are lists and tuples, all oprations on lists and tuples are applicable (like maybe you wanna assign fetchall reult to a list and iterate through it with a for loop
