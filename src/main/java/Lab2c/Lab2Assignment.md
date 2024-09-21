COMP 3111 Lab 2
---

Student ID : <ins>20953394</ins>   
Name : <ins>WONG Kwan</ins>

---

### Part 1 : [`Book.java`]
```java
package Lab2b;

/*  Comp3111LEx\Lab2b\Book.java
Book class for lab2 Exercise 2  */

public class Book {
private String chapters[];
private static final int DEFAULT_CHAPTERS = 10;

    public Book() {
        chapters = new String[DEFAULT_CHAPTERS];
        for (int i = 0; i < chapters.length; i++)
            chapters[i] = "n/a";
    }
    public Book(String argument[]) {
        /* construct the object with an array of chapter names */
        /* PLEASE ADD YOUR CODE HERE */

        chapters = new String[argument.length];
        for (int i = 0; i < argument.length; ++i)
            chapters[i] = argument[i];
    }
    public String getChapter(int i) {
        /* return the chapter by the given index */
        /* PLEASE ADD YOUR CODE HERE */

        if (i < DEFAULT_CHAPTERS) return chapters[i];
        else return "";
    }
    public String[] getChapters() {
        return chapters;
    }
}
```

---

### Part 2 : [`MobileComputer.java`]
```java
package Lab2c;

/*  Comp3111LEx\Lab2c\MobileComputer.java
    Inheritis from Computer, class library for Lab2 Exercise 3   */

public class MobileComputer extends Computer implements Chargeable {
    private int battery;
    public MobileComputer() {
        secret = "MobileComputer secret";
        battery = 5;
    }
    @Override
    public void work() {
        if (battery > 0) {
            System.out.println("It is working on my lap.");
            battery--;
        } else
            System.out.println("Running out of battery");
    }
    public void charge() {
        if (battery < 10)
            battery++;
            System.out.println("Charge this mobile computer");
    }
}
```
> #### Explanation :
> In `MoblieComputer.java` on **line 6**, `implements Chargeable` is added so that the *class* `MobileComputer` implements the *interface* `Chargeable`.  
> Therefore, `m` can now be considered as a `Chargeable` and the code `c.charge(m)` no longer causes error as `m` matches the type `Chargeable` of the input of the *method* `charge()` of `Charger c`.