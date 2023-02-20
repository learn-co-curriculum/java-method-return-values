# Return Values

## Learning Goals

- Discuss return types and return values.

## Methods with Return Types

Let's continue with the block part example from before.

Assume the neighborhood wants to get a headcount of the guests to see how many
people attended the party. Let's write a method to get the headcount:

```java
public class MethodExample {

    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void farewell() {
        System.out.println("Thanks for coming neighbors!");
        System.out.println("See you next year!");
    }

    public static void cook(String food, int quantity) {
        System.out.println("Okay, I can cook " + quantity + " " + food);
    }

    // New method with return statement
    public static int headcount() {
        return 20;
    }

    public static void main (String[] args) {
        welcome();
        cook("Hot dogs", 2);    // Call the new method cook()
        farewell();
        int neighbors = headcount();    // Calling the headcount method and assigning to neighbors
        System.out.println("There are " + neighbors + " neighbors in attendance.");
    }
}
```

In the above code, we created a new method called `headcount()`. Let's look at
the method header of this method:

![method-header](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-with-return-values/method-header-return-type.png)

This method does not take any parameters like the methods we just looked at, but
it does not have a `void` return type. This means the `headcount()` method is
intending on returning something.

A method can return a value after it's done executing. In Java, we want to
specify what data type is to be returned once the method has completed. We call
this a **return type**. It may return another object, a primitive, or even
nothing! As we have seen, to return nothing, we use the return type `void`. But
when we are returning something, we need to specify what data type we are
returning.

In the `headcount()` method, the method header specifies that it will be
returning an `int` data type. This means it _must_ return an `int` data type. If
it doesn't, we'd end up with a compiler-error saying:

```text
java: missing return statement
```

The `return` statement is used to return a specific value from a method. Note
that the `return` keyword interrupts the execution of the current method and
returns the specified value to the caller (i.e. the method that called this
method). In this example, we are expected to return an `int` data type. Hence,
we return the value `20`.

Also notice that since the `headcount()` method returns an `int`, we can assign
the returned integer value to a new variable where the method is called:
`int neighbors = headcount()`;

Let's step through the code one more time to see what happens when the `main()`
method calls the `headcount()` method:

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20MethodExample%20%7B%0A%0A%20%20%20%20public%20static%20void%20welcome%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Welcome%20neighbors!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20farewell%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Thanks%20for%20coming%20neighbors!%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22See%20you%20next%20year!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20cook%28String%20food,%20int%20quantity%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Okay,%20I%20can%20cook%20%22%20%2B%20quantity%20%2B%20%22%20%22%20%2B%20food%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20//%20New%20method%20with%20return%20statement%0A%20%20%20%20public%20static%20int%20headcount%28%29%20%7B%0A%20%20%20%20%20%20%20%20return%2020%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%20%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20welcome%28%29%3B%0A%20%20%20%20%20%20%20%20cook%28%22Hot%20dogs%22,%202%29%3B%20%20%20%20//%20Call%20the%20new%20method%20cook%28%29%0A%20%20%20%20%20%20%20%20farewell%28%29%3B%0A%20%20%20%20%20%20%20%20int%20neighbors%20%3D%20headcount%28%29%3B%20%20%20%20//%20Calling%20the%20headcount%20method%20and%20assigning%20to%20neighbors%0A%20%20%20%20%20%20%20%20System.out.println%28%22There%20are%20%22%20%2B%20neighbors%20%2B%20%22%20neighbors%20in%20attendance.%22%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=17&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

When we click the "Next >" button, just like the other methods, we will see that
it jumps into the `headcount()` method.

What is more interesting is that if we continue clicking "Next >", we will see
the method has a return value of 20.

![return-value-20](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-with-return-values/java-visualizer-return-value-20.png)

Once Java is done executing the `headcount()` method, it will return to the
`main()` method. Since `headcount()` evaluated to 20, it will copy the return
value into the `neighbors` variable:

![return-value-visual](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-with-return-values/method-return-value-visual.png)

Since `headcount()` evaluates to 20, we can choose to do something with the
returned value, like store it in another variable, perform a calculation, or
simply print it like so: `System.out.println(headcount());` If we do nothing
with the return value, IntelliJ will warn:

![ignored-result](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-with-return-values/return-value-ignored.png)

Since we are storing the `headcount()` result in the `neighbors` variable, we
won't see this warning in IntelliJ. We can now see that `neighbors` has been
initialized to 20 in the visualizer:

![intiialize-neighbors-variable](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-with-return-values/java-visualizer-initialize-neighbors.png)

When we resume this program, it will print the following output:

```text
Welcome neighbors!
Okay, I can cook 2 Hot dogs
Thanks for coming neighbors!
See you next year!
There are 20 neighbors in attendance.
```

It's important to understand that any statement after a `return` statement
does not get executed. For example, the following code will not compile because
the code after the `return` statement can never be reached by the JVM and is
therefore considered invalid:

```java
    public static int headcount() {
        return 20;
        System.out.println("Thanks for coming!");
    }
```

We could also return a value of a local variable:

```java
    public static int headcount() {
        int count = 20;
        return count;
    }
```

This would still result in `20` being returned.

## Comprehension Check

Consider the following code:

```java
public class GreetingExample {
    public static String greeting(String name) {
        System.out.println("Hello " + name);
    }
}
```

<details>
    <summary>Describe the method above by looking at the method header.</summary>

  <p>Answer: <br>
     <p>The <code>greeting()</code> method takes in one <code>String</code> parameter called <code>name</code> and returns a <code>String</code> value.</p>
  </p>
</details>

<details>
    <summary>There is something wrong with this method. What is it?</summary>

  <p>Answer: <br>
     <p>The method does not return anything.</p>
  </p>

  <p>Since the method specifies a return type of <code>String</code>, it <b>must</b> return a <code>String</code> value.</p>
</details>

<details>
    <summary>How would we fix this method so it doesn't throw an error?</summary>

  <p>Answer: <br>
     <p>We can either:
       <ol type = "a">
         <li>Change the return type from <code>String</code> to <code>void</code></li>
         <li>Have it return a <code>String</code> with the value <code>"Hello " + name</code> instead of printing the message.</li>
       </ol>
     </p>
  </p>

</details>

Consider the following code:

```java
public class VolumeExample {
    public static double calculateVolume(double length, double width, double height) {
        return length * width * height;
    }
    
    public static void main(String[] args) {
        double volume = calculateVolume(6.1, 10.5, 8);
        System.out.println("The volume of the rectangular prism is " + volume);
    }
}
```

<details>
    <summary>What is the variable <code>length</code> assigned to when we call the <code>calculateVolume()</code> method from the <code>main()</code>method?</summary>

  <p>Answer: <br>
     <p>6.1</p>
  </p>

  <p>The first <code>double</code> value that is passed into the <code>calculateVolume()</code> method will be copied into the parameter, <code>length</code>.</p>
  <p>The value of the first <code>double</code> parameter passed in is 6.1.</p>
</details>

<details>
    <summary>What is the variable <code>width</code> assigned to when we call the <code>calculateVolume()</code> method from the <code>main()</code>method?</summary>

  <p>Answer: <br>
     <p>10.5</p>
  </p>

  <p>The second <code>double</code> value that is passed into the <code>calculateVolume()</code> method will be copied into the parameter, <code>width</code>.</p>
  <p>The value of the second <code>double</code> parameter passed in is 10.5.</p>
</details>

<details>
    <summary>What is the variable <code>height</code> assigned to when we call the <code>calculateVolume()</code> method from the <code>main()</code>method?</summary>

  <p>Answer: <br>
     <p>8.0</p>
  </p>

  <p>The third <code>double</code> value that is passed into the <code>calculateVolume()</code> method will be copied into the parameter, <code>height</code>.</p>
  <p>The value of the third <code>double</code> parameter passed in is 8.0.</p>
</details>
<details>
    <summary>What does <code>calculateVolume()</code> evaluate to when the execution returns to the <code>main()</code> method?</summary>

  <p>Answer: <br>
     <p>512.4</p>
  </p>

  <p>The return value (the product of length, width, and height) will be what the <code>calculateVolume()</code> method results in.</p>
  <p>It'll store the return value in the variable <code>volume</code>.</p>
</details>
<details>
    <summary>What does the program output?</summary>

  <p>Answer: <br>
     <p>The volume of the rectangular prism is 512.4</p>
  </p>

  <p>In this program, we call the <code>calculateVolume()</code> method from the <code>main()</code> method. This will take in the three parameters and execute the statement within the <code>calculateVolume()</code> method's code block.</p>
  <p>See the link below to step through the code above:</p>
  <a href="https://pythontutor.com/visualize.html#code=public%20class%20VolumeExample%20%7B%0A%20%20%20%20public%20static%20double%20calculateVolume%28double%20length,%20double%20width,%20double%20height%29%20%7B%0A%20%20%20%20%20%20%20%20return%20length%20*%20width%20*%20height%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20double%20volume%20%3D%20calculateVolume%286.1,%2010.5,%208%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22The%20volume%20of%20the%20rectangular%20prism%20is%20%22%20%2B%20volume%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false">Browser-based Java Visualizer of VolumeExample</a>
</details>

## Writing Methods

Let's look at the `BikeExample` we have been working with in the past few
lessons:

```java
public class BikeExample {

    public static void ride() {
        System.out.println("Whee! Look at me riding my bike!");
    }

    public static void bikeColor(String color) {
        System.out.println("The color of my bike is " + color + "!");
    }

    public static void main(String[] args) {
        ride();
        bikeColor("red");
    }
}
```

Consider we want to add a new method called `trick` that takes in no parameters
and returns a `String` containing the message "No handlebars!"

<details>
    <summary>What would the method header look like for this described method?</summary>

  <p>Answer: <br>
     <p><code>public static String trick()</code></p>
  </p>

</details>

<details>
    <summary>Where will we write method?</summary>

  <p>Answer: <br>
     <p>Outside the <code>main()</code> method and outside the <code>ride()</code> and <code>bikeColor()</code> method.</p>
  </p>

  <p>This is so we can eventually call the method.</p>
</details>

<details>
    <summary>What would the body of this method look like?</summary>

  <p>Answer: <br>
     <p><code>return "No handlebars!"</code></p>
  </p>

  <p>This one statement would go within the curly braces of the <code>trick()</code> method.</p>
</details>

Assume we want to print this message to the console after the `bikeColor()`
message.

<details>
    <summary>How do we call our new method?</summary>

  <p>Answer: <br>
     <p>We call it within the <code>main()</code> method.</p>
     <p>We'll write <code>System.out.println(trick());</code> in the <code>main()</code> method to call the <code>trick()</code> method while printing it to the console.</p>
  </p>

  <p>We call a static method by writing out the method name and its parameters where we want to execute the method's block statements.</p>
</details>

<details>
    <summary>What does the final version of the program look like?</summary>

  <p>Answer: <br>
     <img src="https://curriculum-content.s3.amazonaws.com/java-mod-1/methods-with-return-values/bike-example-return-value.png">
  </p>

</details>
<details>
    <summary>What is the output when we run this program?</summary>

  <p>Answer: <br>
     <p>Whee! Look at me riding my bike!<br>The color of my bike is red!<br>No handlebars!</p>
  </p>
</details>

## Conclusion

We now know how to read, call, and write methods that return a value. We also
learned about the `return` statement and how it works.
