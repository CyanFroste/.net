### EXAMPLE
```
using System;

namespace TestApplication {
    class AnyClass {

        // Comment 
        /* Main Function */
        static void Main(String[] args){
            
            /* display on Console */
            Console.WriteLine("I beg to differ!");
            Console.ReadKey();

        }
    }
}
```

### CLASS, OBJECTS AND METHODS
```
using System;

namespace RectangleApplication {
    class Rectangle {

        double length;
        double width;
        
        public void setValues() {
            length = 4.5;    
            width = 3.5;
        }
        public double getArea() {
            return length * width; 
        }
        public void display() {
            Console.WriteLine("Length: {0}", length);
            Console.WriteLine("Width: {0}", width);
            Console.WriteLine("Area: {0}", getArea());
        }
    }

    class ExecuteRectangle {
        static void Main(string[] args) {
            // Object Creation
            Rectangle r = new Rectangle();
            r.setValues();
            r.display();
            Console.ReadLine(); 
        } 
    }
}
```
### USING KEYWORD

- Used to Include Namespaces

### DATA TYPES

- Object Type
```
object obj;
obj = 100; // Boxing - value is converted to object
```

- Dynamic Type
```
dynamic varName = 100;
dynamic varName = "Cyan";
```

- Pointer Type
```
char* charPtr;
int* intPtr;
```

### TYPE CONVERSION

- Casting
```
double doub = 6969.69;
int num = (int)doub;
Console.WriteLine(num);     // 6969
```

- Using Methods
```
varName.ToInt;
varName.ToString;
```

### READING DATA FROM USER
Default datatype is String
```
String name = Console.ReadLine();
int num = Convert.ToInt(Console.ReadLine());
```

### CONSTANTS
```
const String name = @"Cyan \Froste";

// Here, when using the @ notation, \ is not treated as an escape sequence
```

### IF, ELSE IF, ELSE

```
if (condition 1) {
   
} else if (condition 2) {
   
} else {
   
}
```

## LOOPS
### WHILE
```
while (condition) {

}
```

### FOR
```
for (int i=0; i<n; i++){

}
```
### DO WHILE
```
do {

} while (condition);
```

## ACCESS SPECIFIERS

- public
- private
- protected
- internal

Default : private

## METHODS

```
private int functionName(parameterOne, parameterTwo){

    return 1;
}
```


Method CCall
```
functionName(a, b);
```

### Parameter Passing
- By Reference
```
public void swap (ref int x, ref int y){
    int temp;
    temp = x; 
    x = y;  
    y = temp;
}

swap(ref a, ref b);     // swaps the actual value of a and b
```

- By value
    uses local variables

- By Output
```
public returnValues(out int a, out int b) {
    a = 5;
    b = 6;    
}

int x, y;
returnValues(out x, out y);     // assigns x = 5 and y = 6
```

## NULLABLES
Can store specified data types as well as null

```
int? num1 = null;
int? num2 = 45;
double? num3 = new double?();
bool? boolval = new bool?();
```

### NULL COALESCING OPERATOR ??
Always returns operand 1 unless operand 1 is null

```
double? num1 = null;
double? num2 = 3;
double num3;

num3 = num1 ?? 5;      
Console.WriteLine(" Value of num3: {0}", num3);     // 5

num3 = num2 ?? 5;
Console.WriteLine(" Value of num3: {0}", num3);     // 3
```

## ARRAYS

### DECLARATION
```
int[] nums = {1, 2, 3, 4};
String[] names = {"rick", "morty"};
double[] balance = new double[10];
int [] marks = new int[5]  { 99,  98, 92, 97, 95};
```

### FOREACH LOOP
```
int[] nums = new int[10];
foreach(int i in nums){

}
```

### TYPES
MULTIDIMENSIONAL
```
string [,] names;
int [ , , ] nums;

// initializing

int [,] a = new int [3,4] {
   {0, 1, 2, 3} ,   
   {4, 5, 6, 7} ,  
   {8, 9, 0, 1}
};

```

JAGGED
```
int [][] scores;

int[][] scores = new int[5][];
for (int i = 0; i < scores.Length; i++) {
   scores[i] = new int[4];
}

// initializing

int[][] scores = new int[2][]{new int[]{92,93,94},new int[]{85,66,87,88}};
```

PARAMETER ARRAYS
```
// method
public int addElements(params int[] arr) {
    int sum = 0;
    
    foreach (int i in arr) {
        sum += i;
    }
    return sum;
}

// driver
static void Main(string[] args) {
    ParamArray app = new ParamArray();
    int sum = app.addElements(512, 720, 250, 567, 889);    
    Console.WriteLine("The sum is: {0}", sum);
}

```

### STRING

```
string name = "Cyan";

// string property
int size = name.Length
```
String is just an array of characters
```
string name = "black"
Console.WriteLine(char[4]);     // returns 'l'
```
 
### STRUCTURES
```
struct colors{
    public string name;
    public int hexValue;

    // can contain methods
    public setValues(string name, int value){
        name = name;
        hexValue = value;
    }
};

```

### ENUMS
```
enum Days = { Sun, Mon, tue, Wed, thu, Fri, Sat };
// each value represents corresponding numbers
int painfulday = (int)Days.Mon      // 1
```

## CLASSES

```
class Jelly {
    public Jelly(){
        // Constructor
    }

    ~Jelly(){
        // Destructor, Deletes the class at the end of the run
    }
}
```

## INHERITANCE
```
class Shape{
    // members
}
interface Dimension{
    // members
}
class Circle : Shape{
    // inherits members of shape too
}
class Square : Shape, Dimension{
    // inherits a class as well as interface
}
```
C# doesn't support multiple inheritance of classes but do so for interfaces


## POLYMORPHISM
- Overloading
- Dynamic Polymorphism - Implemented by Abstract classes and virtual functions
```
abstract class Shape {
    public abstract int area();
}
   
class Rectangle : Shape {
      
    public override int area () { 
        // define here
    }
}
```

```
class Shape {
    public virtual int area() {
        // definition
    }
}
class Rectangle: Shape {
    public Rectangle( ): base( parameter ) { // base is just like a super call in java

    }
    public override int area () {
        // new definition here
    }
}
```

### OVERLOADING OPERATORS
In C# even operators can be overloaded
```
class Box {
    private double length;   
    private double breadth; 
    private double height;
}

public static Box operator+ (Box x, Box y) {
   Box box = new Box();
   box.length = x.length + y.length;
   box.breadth = x.breadth + y.breadth;
   box.height = x.height + y.height;
   return box;
}

// now + adds two box objects

Box a = new Box();
Box b = new Box();
Box c = new Box();

Box c = a + b;
```

### NAMESPACES
A namespace is designed for providing a way to keep one set of names separate from another. The class names declared in one namespace does not conflict with the same class names declared in another.

### PREPROCESSOR DIRECTIVES

```
#define PI 
using System;

namespace PreprocessorCheck {
   class Program {
      static void Main(string[] args) {
        #if (PI)
            Console.WriteLine("PI is defined");
        #else
            Console.WriteLine("PI is not defined");
        #endif
            Console.ReadKey();
        }
    }
}
```

### EXCEPTIONS

- try
- catch
- finally
- throw


## PROPERTIES
```
class Shape {
    private int Length;

// Declare a Code property of type int:
public int Length {
    get {
        return length;      // get accessor
    } set {
        length = value;     // set accessor
    }
}
```

### INDEXERS
```
class IndexedNames {
    private string[] namelist = new string[size];
    static public int size = 10;
    
    public IndexedNames() {
        for (int i = 0; i < size; i++)
        namelist[i] = "N. A.";
    }
    public string this[int index] {
        get {
            string tmp;
        
            if( index >= 0 && index <= size-1 ) {
                tmp = namelist[index];
            } else {
                tmp = "";
        }        
        return ( tmp );

        } set {
            if( index >= 0 && index <= size-1 ) {
                namelist[index] = value;
            }
        }
    }
}
```

### DELEGATES
Similar to pointers. They are Function pointers.
```
namespace DelegateApp {

    delegate void NumberChanger(int n);
    class Test {
        static int num = 10;
        
        public static void AddNum(int p) {
            num += p;
            Console.WriteLine("Named Method: {0}", num);
        }
        
        static void Main(string[] args) {       
            
            //instantiating the delegate using the named methods 
            nc =  new NumberChanger(AddNum);
            
            //calling the delegate using the named methods 
            nc(5);
        }
    }
}
```
### EVENTS
```
```
### COLLECTIONS
- ArrayList
- Hashtable
- Stack
- Queue 
### GENERICS
```
```
### ANONYMOUS METHODS
```

namespace DelegateApp {

    delegate void NumberChanger(int n);
    class Test {
        static int num = 10;
        
        public static void AddNum(int p) {
            num += p;
            Console.WriteLine("Named Method: {0}", num);
        }
        
        static void Main(string[] args) {

            //create delegate instances using anonymous method

            NumberChanger nc = delegate(int x) {
                Console.WriteLine("Anonymous Method: {0}", x);
            };
            
            //calling the delegate using the anonymous method 
            nc(10);
            
            //instantiating the delegate using the named methods 
            nc =  new NumberChanger(AddNum);
            
            //calling the delegate using the named methods 
            nc(5);
        }
    }
}
```