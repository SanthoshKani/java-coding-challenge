# java-interview-questions

## What is the output of the following java program?

### Q1
```
public class Main {
    public static int temp1 = 1;
    private static int temp2 = 2;
    public int temp3 = 3;
    private int temp4 = 4;

    public static class Nested {
        private static int temp5 = 5;
        private static int getSum() {
            return (temp1 + temp2 + temp3 + temp4 + temp5);
        }
    }

    public static void main(String[] args) {
        Main.Nested obj = new Main.Nested();
        System.out.println(obj.getSum());
    }
}
```
#### Choices
```
a) 15
b) 9
c) 5
d) Compilation Error
```
```
Compilation Error: (Non-static field 'temp3' cannot be referenced from a static context)
```

### Q2
```
public class Main {
    public static void gfg(String s) {
        System.out.println("String");
    }

    public static void gfg(Object o) {
        System.out.println("Object");
    }

    public static void main(String args[]) {
        gfg(null);
    }
}
```
#### Choices
```
a) Object
b) String
c) NullPointerException thrown
d) Compilation Error
```
```
String: Method Overloading - the most specific method is chosen at compile time.
```

### Q3
```
public class Main {
    private int data = 10;

    class Nested {
        private int data = 20;

        private int getData() {
            return data;
        }

        public void main(String[] args) {
            Nested nested = new Nested();
            System.out.println(nested.getData());

        }
    }

    private int getData() {
        return data;
    }

    public static void main(String[] args) {
        Main main = new Main();
        Nested nested = main.new Nested();
        System.out.printf("%d", main.getData());
        nested.main(args);
    }
}
```
#### Choices
```
a) 1020
b) 2010
c) Runtime Error
d) Compilation Error
```
```
1020
```
### Q4
```
public class Test implements Runnable {
    @Override
    public void run() {
        System.out.printf(" Arcsight ");
    }

    public static void main(String[] args) throws InterruptedException
    {
        Thread runnableThread = new Thread(new Test());
        runnableThread.start();
        runnableThread.start();
        System.out.println(runnableThread.getState());
    }
}
```
#### Choices
```
a) Runtime Error: InterrupteException
b) Runtime Error: IllegalThreadStateException
c) Runtime Error: IllegalArgumentException
d) Runtime Error: IllegalStateException
```
```
Runtime Error: IllegalThreadStateException
```
### Q5
```
public class Except {
    public static void main(String[] args) {
        try {
            throw new Error();
        } catch (Error e) {
            try {
                throw new RuntimeException();
            } catch (Throwable t) {
            }
        }
        System.out.println("phew");
    }
}
```
#### Choices
```
a) phew
b) Error instance thrown
c) Runtime Error
d) None of the above
```
```
phew
```
### Q6
```
public class Test {
    int varA = 10;
    static int varB = 20;

    public static void main(String[] args) {
        Test testObj1 = new Test();
        Test testObj2 = new Test();

        testObj1.varA = 100;
        testObj1.varB = 200;

        System.out.println("testObj1.a =" + testObj1.varA + " testObj1.b =" + testObj1.varB);
        System.out.println("testObj2.a =" + testObj2.varA + " testObj2.b =" + testObj2.varB);
    }
}
```
#### Choices
```
a) t1.a=100 t1.b=200, t2.a=10 t2.b=200
b) t1.a=10 t1.b=200, t2.a=10 t2.b=200
c) t1.a=100 t1.b=200, t2.a=10 t2.b=20
d) t1.a=100 t1.b=200, t2.a=100 t2.b=200
```
```
t1.a=100 t1.b=200, t2.a=10 t2.b=200
```
### Q7
```
public class Test implements Runnable {
    @Override
    public void run() {
        System.out.printf("%d",3);
    }

    public static void main(String[] args) throws InterruptedException {
        Thread thread = new Thread(new Test());
        thread.start();
        System.out.printf("%d",1);
        thread.join();
        System.out.printf("%d",2);
    }
}
```
#### Choices
```
a) 123
b) 312
c) 132
d) 321
```
```
132
```
### Q8
```
public class Test extends Thread {
    public void run() {
        System.out.printf("Test ");
    }

    public static void main(String[] args) {
        Test test = new Test();
        test.run();
        test.start();
    }
}
```
#### Choices
```
a) Compilation error
b) Runtime error
c) Test
d) Test Test
```
```
Test Test
```
### Q9
```
public interface Test {
    public int calculate();

    protected interface NestedInterface {
        public void nested();
    }
}
```
#### Choices
```
a) Compile time error due to NestedInterface
b) Compile time error due to access modifier of NestedInterface
c) No Compile time error
d) NestedInterface cannot hold any function declaration.
```
```
Compile time error due to access modifier of NestedInterface
```
### Q10
```
public class Test {
    public static void main(String[] args) {
        static int arr1[] = {11, 22, 33};
        static int arr2[] = {11, 22, 33, 44, 55};
        static int ptr[];
        ptr = arr1;
        arr1 = arr2;
        arr2 = ptr;
        System.out.print(arr1.length + " ");
        System.out.println(arr2.length);
    }
}
```
#### Choices
```
a) Compile time error
b) 5 3
c) 3 5
d) 5 5
```
```
Compile time error due to access modifier of NestedInterface
```
