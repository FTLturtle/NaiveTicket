NOTE TO GRADER: many of my code segments appear to be on the same line. This is only because I didn't figure out until exercise 40 how to get the .md file to show code fragments properly, and not because I think it's a good idea to write method declarations all on one line. If you go view this markdown file in the editor, you will see that I have actually split the code up into separate lines.

# NaiveTicket

The second Objects lab, from the BlueJ book's second chapter.

Look for the [Chapter 2 file](./doc/BlueJ-objects-first-ch2.pdf) you need in the [doc](./doc) folder.
There is 35 pages of reading and exercises in the chapter.

Work through all these exercises. You edit this file with your answers for these exercises.

### Exercise 2.1
* Create a TicketMachine object on the object bench.
* Upon viewing its methods, `getBalance`, `getPrice`, `insertMoney`, `printTicket`.
* Use `getPrice` method to view the value of the price of the tickets that was set when this object was created.
* Use `insertMoney` method to simulate inserting an amount of money into the machine.
* Use `getBalance` to check that the machine has a record of the amount inserted.
	* You can insert several separate amounts of money into the machine, just like you might insert multiple coins or notes into a real machine. Try inserting the exact amount required for a ticket. As this is a simple machine, a ticket will not be issued automatically, so once you have inserted enough money, call the `printTicket` method. A facsimile ticket should be printed in the BlueJ terminal window.

Done

### Exercise 2.2
* What value is returned if you check the machine’s balance after it has printed a ticket?

The value returned is 0.

### Exercise 2.3
* Experiment with inserting different amounts of money before printing tickets.
	* Do you notice anything strange about the machine’s behavior?
	* What happens if you insert too much money into the machine – do you receive any refund?
	* What happens if you do not insert enough and then try to print a ticket?

Whenever the `printTicket` method is called, the balance is set to 0 and a ticket is printed, regardless of what the balance is or whether it is more or less than the ticket price.

Done

### Exercise 2.4
* Try to obtain a good understanding of a ticket machine’s behavior by interacting with it on the object bench before we start looking at how the `TicketMachine` class is implemented in the next section.

Done

### Exercise 2.5
* Create another ticket machine for tickets of a different price.
	* Buy a ticket from that machine.
	* Does the printed ticket look different?

Yes, the ticket looks different when the ticket price is set to a different amount. The amount is listed on the third line of text of the ticket.

### Exercise 2.6
* Write out what you think the outer wrappers of the `Student` and `LabClass` classes might look like – do not worry about the inner part.

the outer wrappers of the `student` and `labClass` classes might look like the following:

`public class Student{}`

`public class LabClass{}`

### Exercise 2.7
Does it matter whether we write<br>
`public class TicketMachine`<br>
or<br>
`class public TicketMachine`<br>
in the outer wrapper of a class?

Yes, it does.

* Edit the source of the `TicketMachine` class to make the change and then close the editor window.
	* Do you notice a change in the class diagram?
	* What error message do you get when you now press the compile button?
	* Do you think this message clearly explains what is wrong?

The class diagram now has red crosshatching on it, indicating an error.

The three error messages given are two `<identifier> expected` errors on the line containing the class signature and one `invalid method declaration; return type required` on the line containing the method signature of the constructor method.

These error messages do not clearly explain exactly what is wrong (that the class signature is written improperly), but they definitely point you in the right direction. For example, seeing the identifier expected error would imply that you simply need to add an identifier to fix the error, but doing that would not actually fix the error. However, the identifier expected error does indicate that the class signature is written improperly, and knowing that, you can look at the class signature and see that the words class and public are out of order, leading you to actually fixing the problem.

The fact that the constructor method signature has an error asking you for a return type, means that the IDE is not recognizing it as a constructor, because constructors do not need to specify a return type.

### Exercise 2.8
* Check whether or not it is possible to leave out the word `public` from the outer wrapper of the `TicketMachine` class.

It is possible to leave out the word `public`. The code compiles successfully, and the object created by that class seems to act the same way without public as it did with public.

### Exercise 2.9
* From your earlier experimentation with the ticket machine objects within BlueJ you can probably remember the names of some of the methods – `printTicket`, for instance.
	* Look at the class definition in Code 2.1 and use this knowledge, along with the additional information about ordering we have given you, to try to make a list of the names of the fields, constructors, and methods in the `TicketMachine` class.
	* Hint: There is only one constructor in the class.

Fields: private int price, private int balance, private int total
Constructors: public TicketMachine(int ticketCost)
Methods: public int getBalance(), public void insertMoney(int amount), public void printTicket()

### Exercise 2.10
* Do you notice any features of the constructor that make it significantly different from the other methods of the class?

The constructor has the same name as the class, it has no return type, and it is the only method that is capitalized.

### Exercise 2.11
* What do you think is the type of each of the following fields?

```java
private int count;
private Student representative;
private Server host;
```

int, Student, Server.

### Exercise 2.12
* What are the names of the following fields?

```java
private boolean alive;
private Person tutor;
private Game game;
```
alive, tutor, game.

### Exercise 2.13

In the following field declaration from the TicketMachine class<br>

```java
private int price;
```
does it matter which order the three words appear in?
* Edit the `TicketMachine` class to try different orderings. After each change, close the editor.
	* Does the appearance of the class diagram after each change give you a clue as to whether or not other orderings are
possible?
	* Check by pressing the compile button to see if there is an error message.
	* Make sure that you reinstantiate the original version after your experiments!

yes it matters. 

### Exercise 2.14
* Is it always necessary to have a semicolon at the end of a field declaration?
* Once again, experiment via the editor.
* The rule you will learn here is an important one, so be sure to remember it.

yes.

### Exercise 2.15
* Write in full the declaration for a field of type `int` whose name is `status`.

int status;

### Exercise 2.16
* To what class does the following constructor belong?
```
public Student(String name)
```
class Student.

### Exercise 2.17
* How many parameters does the following constructor have and what are their types?
```
public Book(String title, double price)
```

two parameters. The types are String and double.

### Exercise 2.18
* Can you guess what types some of the `Book` class’s fields might be?
* Can you assume anything about the names of its fields?

Strings for text, ints for page numbers.

the names will be indicators for what the fields are. Maybe things like pageNumber, and text.

Work all Exercises from 2.19 to 2.58 that are **NOT** marked *Challenge exercise*.
READ upto and INCLUDING section 2.15 of this chapter.

2.19
this.name = petsName;

2.20
The problem is that you declare a new int price that is limited to the scope of the constructor method, and you assign ticketCost to that. Thus, the object field price is never set.

2.21
They are exactly the same structure, just used to access different fields.

2.22
'what is the current balance on the ticket machine?'

2.23
No it does not.

2.24
public int getTotal(){
	return total;
}

2.25
missing return statement

2.26
one returns a value, while the other one doesn't (it simply prints content to the terminal);

2.27
No. They don't need them, they are used to change the values of the fields among other things. They have the keyword void in the method signature.

2.28
Done

2.29
the fact that it has a return type immediately tells us that it cannot be a constructor.

2.30
`public void setPrice(int ticketCost){
	this.price = ticketCost;
}`

2.31
this.score = this.score + points;

2.32
this.price = this.price - amount.

2.33
public void prompt(){
	System.out.println("Please insert the correct amount of money.");
}

2.34
public void showPrice(){
	System.out.printf("The price of a ticket is %d cents.", this.price);
}

2.35
Different. This is because price is an instance variable, and these two instances have been constructed with different values for price.

2.36
It would print out the word price instead of the value of the price variable. "# price cents."

2.37
The same as above.

2.38
No. The way the showPrice methods are written, they are instance (non-static) methods that only access the value of price in their own instance.

2.39
public TicketMachine(){
    this.price = 1000;
    this.balance = 0;
    this.total = 0;
}

This has the effect that BlueJ no longer asks for the ticketPrice.

2.40
```java
public void empty(){  
    this.total = 0;  
}  
```

This method does not need to take any parameters.

This method is a mutator, because it changes (or mutates) the value of a field.

2.41
```java
public void setPrice(int newPrice){
	this.price = newPrice;
}
```

Yes, this method is a mutator.

2.42
```java
public TicketMachine(){
	this(1000); // default value of price is 1000 cents
}

public TicketMachine(int ticketPrice){
	this.price = ticketPrice;
	this.balance = 0;
	this.total = 0;
}
```

starting with exercise 2.43, the chapter asks us to use the better-ticket-machine project, which I found at the following GitHub address: https://github.com/miguelbayon/better-ticket-machine/blob/master/TicketMachine.java

I then forked it to my own GitHub account, and cloned it to my local machine. It's GitHub address is this: https://github.com/FTLturtle/better-ticket-machine

2.43
TicketMachine behaves as described. When an error message is reported, the balance does not change. if I enter zero, most likely an error message will tell me that i need to enter a positive value, and the value of balance will not be changed.

My guess was correct.

2.44
In this case, entering zero as an argument when calling insertMoney will not cause an error message, and the method will run normally. This is not a problem, since adding zero will simply leave the balance the same as it was before, which is what you would want the method to do anyway.

2.45
The boolean in the shapes project was boolean isVisible, which controlled whether or not the circle object was visible on the canvas.

Yes, this feature was well suited to being controlled by a type with only two different values, since the circle can only have two states of visibility - visible and invisible.

2.46
```java
total = total + balance;
balance = 0;
```

vs

```java
total = total + price;
balance = balance - price;
```

in the first case, the total is always updated by the balance, and the balance is always reset to 0, causing strange behavior that is unwanted in a ticket machine. In the second case, the total is updated by the price of the ticket that was just printed, and the balance is updated by subtracting the price of the ticket that was just printed. Clearly the second case is better behavior for a ticket machine, because it avoids the problems of printing tickets that have not been fully paid for as well as the machine simply stealing the money of the customer if they put in more money than necessary to purchase the ticket.

2.47
No, because the method checks to make sure that balance is equal to or greater than price before subtracting price. Thus, balance can never go below zero simply by subtracting price.

2.48
Appendix D not provided. However, docs.oracle.com/javase/tutorial/java/nutsandbolts/opsummary.html provides the following reference guide:

```
The Java Tutorials have been written for JDK 8. Examples and practices described in this page don't take advantage of improvements introduced in later releases.

Summary of Operators
The following quick reference summarizes the operators supported by the Java programming language.

Simple Assignment Operator
=       Simple assignment operator
Arithmetic Operators
+       Additive operator (also used
        for String concatenation)
-       Subtraction operator
*       Multiplication operator
/       Division operator
%       Remainder operator
Unary Operators
+       Unary plus operator; indicates
        positive value (numbers are 
        positive without this, however)
-       Unary minus operator; negates
        an expression
++      Increment operator; increments
        a value by 1
--      Decrement operator; decrements
        a value by 1
!       Logical complement operator;
        inverts the value of a boolean
Equality and Relational Operators
==      Equal to
!=      Not equal to
>       Greater than
>=      Greater than or equal to
<       Less than
<=      Less than or equal to
Conditional Operators
&&      Conditional-AND
||      Conditional-OR
?:      Ternary (shorthand for 
        if-then-else statement)
Type Comparison Operator
instanceof      Compares an object to 
                a specified type 
Bitwise and Bit Shift Operators
~       Unary bitwise complement
<<      Signed left shift
>>      Signed right shift
>>>     Unsigned right shift
&       Bitwise AND
^       Bitwise exclusive OR
|       Bitwise inclusive OR
```

2.49
