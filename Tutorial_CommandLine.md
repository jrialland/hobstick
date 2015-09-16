# Download hobstick #

Download the latest `hobstick-x.y.jar` from [downloads](http://code.google.com/p/hobstick/downloads/list).

# Prepare Database Script #

Create a simple database script.  For example, lets make a database about food preferences of some random people.

Create a file named `food.pl` using your favorite text editor (e.g. `vi food.pl`) and paste this content:
```
eats(fred,oranges).        % "Fred eats oranges"
eats(fred,t_bone_steaks).  % "Fred eats T-bone steaks"

eats(tony,apples).         % "Tony eats apples"

eats(john,apples).         % "John eats apples"
eats(john,grapefruit).     % "John eats grapefruit"
```

# Load hobstick #

Start the hobstick interpreter with this database script:
```
java -jar hobstick-x.y.jar food.pl
```

If the database compiles, you will be presented with a prompt, from which you can begin to enter a query:
```
?- 
```

# Queries #

We can now ask hobstick some questions about `food.pl`:

Does fred eat oranges?
```
?- eats(fred,oranges).

Yes
```

Does mike eat apples?
```
?- eats(mike,apples).

No
```

Who eats apples?
```
?- eats(Who,apples).
Who=tony
 
```
so tony eats apples.  At this point hobstick is waiting for us to decide if we want to search for another solution, or to stop.  To search for another solution, enter `; RETURN`:
```
 ;
Who=john
 .
```
and john also eats apples.  At this point hobstick identified there are no more solutions, so it displays `.` and a new prompt.

# See Also #

See other [Prolog tutorials](http://www.google.com/search?q=prolog+tutorial).  hobstick implements most basic Prolog syntax.