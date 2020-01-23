### BASIC SYNTAX
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
 