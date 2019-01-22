# Active Record!  Rejoice!

## Prompt:
For tonights homework we'll be revisiting the Cheesy SQL homework, but doing it with ActiveRecord!  This assignment has two parts:

## Part 1: ActiveRecord-fying SQL:

For this part you should edit this README.md. Take a look at each of the SQL commands and determine the ActiveRecord commands that should replace those SQL commands.  For each question replace the `#your active record solution` with the ActiveRecord command that does the same thing as the SQL command.

If you have any questions, or see anything you haven't seen yet, the [documentation](https://guides.rubyonrails.org/active_record_basics.html) for Rails is wonderful.

For all solutions, pretend that you have a model called `Cheese`.

#### Add these cheeses to your database:

- Roquefort, a yellow french cheese with a stink level of 5
  ```sql
  INSERT INTO cheeses (name, color, origin, stink_level) VALUES ('Roquefort', 'yellow', 'French', 5);
  ```

  ```ruby
  cheeese.cereate({name: " Roquefort" , color: "yellow" , origin: " French" ,stink_level: 5}) ```

- Charolais, a white french cheese with a stink level of 5
  ```sql
  INSERT INTO cheeses (name, color, origin, stink_level) VALUES ('Charolais', 'white', 'French', 5);
  ```

  ```ruby
  cheeese.cereate({name: " Charolais" , color: "white" , origin: " French" ,stink_level: 5}) 
  ```

- Hooligan, a yellow American cheese with a stink level of 3
  ```sql
  INSERT INTO cheeses (name, color, origin, stink_level) VALUES ('Hooligan', 'yellow', 'American', 3);
  ```

  ```ruby
  cheeese.cereate({name: " Hooligan" , color: "yellow" , origin: " American" ,stink_level: 3}) 
  ```
- Teleme, a white american cheese with a stink level of 2
  ```sql
  INSERT INTO cheeses (name, color, origin, stink_level) VALUES ('Teleme', 'white', 'American', 2);
  ```

  ```ruby
  cheeese.cereate({name: " Teleme" , color: "white" , origin: " American" ,stink_level:2}) 
  ```
- And then we inserted a few more cheeses, but I think you get the point.  Moving on!

#### Choosing Cheese


- Find all the cheeses
  
  ```sql
  SELECT * FROM cheeses;
  ```

  ```ruby
  cheese.all
```

- Find all the French cheeses
    
  ```sql
  SELECT name FROM cheeses WHERE origin = 'French';
  ```

  ```ruby
  cheese.where({ origin : "French"})
  ```
- Find all the English cheeses
    
  ```sql
  SELECT name FROM cheeses WHERE origin = 'English';
  ```

  ```ruby
  cheese.where({ origin : "English"})
  ```
- Find all cheeses with a stink level of 2
    
  ```sql
  SELECT name FROM cheeses WHERE stink_level = 2;
  ```

  ```ruby
  cheese.where({ stink_level : 2})
  ```
- Find all cheeses with a stink level of 10
    
  ```sql
  SELECT name FROM cheeses WHERE stink_level = 10;
  ```

  ```ruby
  cheese.where({ stink_level : 10})
  ```
- Find all French cheeses with a stink level of 5
    
  ```sql
  SELECT name FROM cheeses WHERE origin = 'French' AND stink_level = 5;
  ```

  ```ruby
  Cheese.where("origin:"French" " ).and(Cheese.where("stink_level = 5"))
```
- Find all Irish cheeses with a stink level of 6
    
  ```sql
  SELECT name FROM cheeses WHERE origin = 'Irish' AND stink_level = 6;
  ```

  ```ruby
  Cheese.where("origin:"Irish" " ).and(Cheese.where("stink_level = 6")) 
  ```
- Find all cheeses with a stink level of at least 4, but no greater than 8.
    
  ```sql
  SELECT name FROM cheeses WHERE stink_level >= 4 OR stink_level <= 8;
  ```

  ```ruby
  Cheese.where("stink_level >= 4 ").or(Cheese.where("stink_level <= 8"))  
  ```
- Find all American and English cheeses.
    
  ```sql
  SELECT name FROM cheeses WHERE origin = 'American' OR origin = 'English';
  ```

  ```ruby
  Cheese.where("origin:"American" " ).or(Cheese.where("origin:"English" ")) 
  ```
- Find all cheeses that are not from France.
    
  ```sql
  SELECT * FROM cheeses WHERE origin NOT IN ('French');
  ```

  ```ruby
  Cheese.find( origin: !French)
```


#### Restocking Cheese

The cheese game is changing constantly. Let's update our cheeses.

- Change the stink level of Roquefort to 3
    
  ```sql
  UPDATE cheeses SET stink_level = 3 WHERE name = 'Roquefort';
  ```

  ```ruby
  # your active record solution
  ```
- Change the color of Teleme to "mauve"
    
  ```sql
  UPDATE cheeses SET color = 'mauve' WHERE name = 'Teleme';
  ```

  ```ruby
  # your active record solution
  ```
- Delete the Hooligan cheese
    
  ```sql
  DELETE from cheeses WHERE name = 'Hooligan';
  ```

  ```ruby
  # your active record solution
  ```
- Change the stink level of Stichelton to be 7
    
  ```sql
  UPDATE cheeses SET stink_level = 7 WHERE name = 'Stichelton';
  ```

  ```ruby
  # your active record solution
  ```
- Add the cheese "Monterey Jack", an American cheese with a stink level of 0
    
  ```sql
  INSERT INTO cheeses (name, color, origin, stink_level) VALUES ('Monterey Jack', 'white', 'American', 0);
  ```

  ```ruby
  # your active record solution
  ```
- Delete Durrus
    
  ```sql
  DELETE FROM cheeses WHERE name = 'Durrus';
  ```

  ```ruby
  durrus.destroy
```

## Part 2: Review Today's Lesson:
Review the `README.md` file from today's lesson [here](https://github.com/WDI-HoneyBadger/w10d03-intro-to-rails) then answer the following questions:

- In express we built our routes inside of our controller, where do you put routes in a rails app?
  ```
     config/routes.rb
```
- Should a rails model be lower-case and plural, upper-case and plural, lower-case and singular, or upper-case and singular?
  ```
     singular name with first letter uppercase
  ```
- What kind of files belong in the `assets` directory?
  ```
     CSS, JavaScript, images, fonts..
  ```
- What does the command `rails db:drop` do?
  ```
      delete database
  ```
- What does the command `rails c` do?
  ```
     open console
  ```
- What is an ORM?  What does it stand for?
```
     Object-relational mapping
  ```
- What does a migration file do?
  ```
     stored in db/migrate  is a change to the database schema
  ```
- How do you run your migration files?
  ```
     rails db:migrate
  ```
- How do you start a rails server?
  ```
    rails s
```
- What is the command to start a new rails API called "reasons_why_ghadeer_rules"?
  ```
    rails new reasons_why_ghadeer_rules -G --database=postgresql
```
- What is an API?
  ```
      one page application without views 
  ```
