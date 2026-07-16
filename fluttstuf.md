# Flutter + Dart: From Zero to Hero

**The complete beginner's guide to building mobile apps.**  
No prior experience required. Start from page 1.

---

## Volume 1: Dart Programming Language

---

### Chapter 1: What is Programming?

#### 1.1 What is code?

Code is a set of instructions written for a computer to follow. Think of it like a recipe:

```
Recipe for tea:
1. Boil water
2. Put tea bag in cup
3. Pour water into cup
4. Wait 3 minutes
5. Remove tea bag
6. Add sugar if desired
```

Code is the same thing — a series of step-by-step instructions. The computer reads them in order and executes each one.

```dart
// This is Dart code (our recipe for the computer)
void main() {
  print('Hello, world!');  // Step 1: Print "Hello, world!"
  print('Welcome to Dart'); // Step 2: Print "Welcome to Dart"
}
```

#### 1.2 What is a programming language?

A programming language is a way to talk to computers. Like human languages (English, Spanish, Urdu), programming languages have:

- **Words** with special meanings (like `print`, `if`, `for`, `class`)
- **Grammar** (syntax) — rules for how to write valid instructions
- **Punctuation** — `{ }` `[ ]` `( )` `;` all have meaning

**Dart** is the programming language we use. It's designed by Google specifically for building apps.

#### 1.3 What is Flutter?

Flutter is a **framework** built with Dart. A framework is a collection of pre-written code that helps you build things faster.

Think of it like:
- **Dart** = the bricks and mortar (raw materials)
- **Flutter** = pre-made walls, windows, doors (building blocks)
- **Your app** = the house you build with them

#### 1.4 What is an app?

An **app** (application) is a program that runs on a device (phone, tablet, computer). It has:
- A **user interface** (UI) — things you see and touch
- **Logic** — what happens when you interact with it
- **Data** — information it stores and uses

#### 1.5 What we'll build

By the end of this guide, you'll understand how to build apps like:
- A Todo list
- A shopping cart
- A weather app
- A social media feed

You'll learn the same patterns used by professional Flutter developers.

---

### Chapter 2: Your First Dart Code

#### 2.1 The `main()` function

Every Dart program starts with a function called `main`. It's the entry point — where the computer begins reading.

```dart
void main() {
  // Your code goes here
}
```

**Line by line breakdown:**

| Code | Meaning |
|------|---------|
| `void` | This function doesn't return a value |
| `main` | The name of the function (reserved — always the start) |
| `()` | Inputs (empty = no inputs needed) |
| `{` | Start of the function body |
| `}` | End of the function body |
| `//` | Comment — notes for humans, ignored by computer |

#### 2.2 Printing text

```dart
void main() {
  print('Hello, world!');
}
```

`print()` is a built-in function that shows text in the console. The text `'Hello, world!'` is called a **string** (a sequence of characters).

**Single quotes vs double quotes:**
```dart
print('Hello');   // Single quotes (common in Dart)
print("Hello");   // Double quotes (also works)
```

#### 2.3 Comments

Comments are notes for yourself and other developers. The computer ignores them completely.

```dart
// This is a single-line comment (two slashes)

/*
  This is a multi-line comment.
  Everything between /* and */ is ignored.
*/

/// This is a documentation comment (three slashes).
/// Used to explain what functions and classes do.
/// Tools can generate documentation from these.
```

#### 2.4 Your first program

```dart
void main() {
  // Print a greeting
  print('Hello, world!');
  
  // Print some math
  print(2 + 3);  // Prints: 5
  
  // Print your name
  print('My name is ${'Alice'}');
}
```

**Run this program.** You should see:
```
Hello, world!
5
My name is Alice
```

---

### Chapter 3: Variables — Storing Information

#### 3.1 What is a variable?

A **variable** is a named box that holds a value. Like a labeled jar:

```
    ┌─────────────┐
    │   "Alice"   │  ← Value
    └──────┬──────┘
           │
      name = "Alice"
      ↑ The label
```

#### 3.2 Declaring variables

```dart
String name = 'Alice';
```

| Part | Meaning |
|------|---------|
| `String` | The **type** (what kind of data) |
| `name` | The **name** (how we refer to it) |
| `=` | Assignment (put value into box) |
| `'Alice'` | The **value** (what's stored) |
| `;` | End of statement |

#### 3.3 Basic types

```dart
String text = 'Hello';           // Text (a string of characters)
int wholeNumber = 42;            // Whole number (no decimal)
double decimal = 3.14;           // Number with decimal
bool trueOrFalse = true;         // Boolean (true or false)
```

**More examples:**

```dart
String firstName = 'Muhammad';
String lastName = "Ali";
int age = 25;
double price = 99.99;
double pi = 3.1415926535;
bool isStudent = true;
bool isEmployed = false;
```

#### 3.4 Type inference with `var`

Instead of writing the type, you can let Dart figure it out:

```dart
var name = 'Alice';    // Dart knows this is a String
var age = 30;           // Dart knows this is an int
var price = 99.99;      // Dart knows this is a double
var isReady = true;     // Dart knows this is a bool
```

**When to use `var` vs explicit types:**
- Use explicit types (`String name`) when the type isn't obvious
- Use `var` when the type is clear from the value

#### 3.5 Changing variable values

Variables declared with `var` or an explicit type CAN be changed:

```dart
var name = 'Alice';
print(name);  // Alice

name = 'Bob';
print(name);  // Bob

name = 42;    // ERROR! name is a String, can't assign int
```

Once a variable has a type, it can only hold values of that type.

#### 3.6 Variables that CAN'T change: `final` and `const`

```dart
final String appName = 'My App';
// appName = 'New Name';  // ERROR! final can't be changed

const double pi = 3.14159;
// pi = 3.0;  // ERROR! const can't be changed
```

**Difference between `final` and `const`:**

```dart
// final — value determined at runtime
final DateTime now = DateTime.now();     // OK (runs when app starts)
final int random = Random().nextInt(100); // OK (computed at runtime)

// const — value must be known before app runs (compile-time)
const double pi = 3.14159;              // OK (known in advance)
const DateTime now = DateTime.now();     // ERROR! (needs to run)
```

**When to use each:**

| Keyword | Use when |
|---------|----------|
| `String name = 'Alice'` | The value will change (e.g., counter, form input) |
| `final String id = 'abc'` | The value is set once at runtime and never changes |
| `const double pi = 3.14` | The value is a fixed constant known at compile time |

#### 3.7 Variables that CAN be null: `?`

By default, Dart variables CANNOT be null. To allow null, add `?`:

```dart
String name = 'Alice';    // NEVER null (can't assign null)
String? maybeNull;        // CAN be null

maybeNull = null;          // OK
maybeNull = 'Hello';       // OK

// name = null;            // ERROR! String can't be null
```

**Why null safety?** Null errors are the #1 cause of crashes in programming. Dart prevents them at compile time.

#### 3.8 Safe access with `?.` and `??`

```dart
String? maybeNull;

// Safe access — if null, return null instead of crashing
int? length = maybeNull?.length;  // null (doesn't crash)

// Default value — if null, use the default
String display = maybeNull ?? 'Guest';  // 'Guest'

// Force unwrap — crash if null (use ONLY when 100% sure)
// print(maybeNull!.length);  // CRASH if null
```

#### 3.9 String interpolation

Insert variables into strings using `$`:

```dart
String name = 'Alice';
int age = 30;

print('Hello, $name');           // Hello, Alice
print('$name is $age years old'); // Alice is 30 years old
print('${name.toUpperCase()}');   // ALICE (expression in braces)
print('Sum: ${2 + 3}');          // Sum: 5
```

**Rule of thumb:** Simple variable → `$name`. Expression → `${name.length}`.

#### 3.10 Practice exercises

**Exercise 1:** Create variables for your name, age, city, and whether you're a student. Print them.

```dart
void main() {
  String name = 'Your Name';
  int age = 25;
  String city = 'Your City';
  bool isStudent = true;
  
  print('Name: $name');
  print('Age: $age');
  print('City: $city');
  print('Student: $isStudent');
}
```

**Exercise 2:** What's the output?

```dart
void main() {
  var x = 10;
  var y = 20;
  var sum = x + y;
  print('$x + $y = $sum');
}
```

Answer: `10 + 20 = 30`

---

### Chapter 4: Data Types In Depth

#### 4.1 Numbers: `int` and `double`

```dart
int count = 10;           // Whole numbers
int negative = -5;        // Negative numbers
int large = 1000000;      // Large numbers (no commas)

double price = 99.99;     // Decimal numbers
double scientific = 1.5e6; // 1.5 × 10^6 = 1500000
double negative = -3.14;  // Negative decimals

// Type conversion
int fromDouble = 3.14.toInt();    // 3 (truncates, doesn't round)
double fromInt = 10.toDouble();   // 10.0

// Math operations
int sum = 10 + 5;       // 15
int diff = 10 - 5;      // 5
int product = 10 * 5;   // 50
double quotient = 10 / 5;  // 2.0 (division returns double)
int intQuot = 10 ~/ 5;  // 2 (integer division)
int remainder = 10 % 3; // 1 (modulo/remainder)
```

#### 4.2 Strings: `String`

Strings are text. They can be created in several ways:

```dart
String single = 'Hello';          // Single quotes
String double = "Hello";          // Double quotes
String both = "It's a car";       // Double quotes allow apostrophe

// Multi-line strings
String multi = '''
This is a
multi-line
string
''';

// String concatenation
String hello = 'Hello' + ' ' + 'World';  // 'Hello World'

// String interpolation
String name = 'Alice';
String greeting = 'Hello, $name!';       // 'Hello, Alice!'

// Common string methods
String text = 'Hello, World!';
print(text.length);           // 13
print(text.toUpperCase());    // 'HELLO, WORLD!'
print(text.toLowerCase());    // 'hello, world!'
print(text.contains('Hello')); // true
print(text.startsWith('He')); // true
print(text.endsWith('!'));    // true
print(text.replaceAll('World', 'Dart')); // 'Hello, Dart!'
print(text.split(','));       // ['Hello', ' World!']
print('  hello  '.trim());    // 'hello' (removes spaces)
```

#### 4.3 Booleans: `bool`

Only two values: `true` and `false`.

```dart
bool isRaining = true;
bool isSunny = false;

// Boolean operators
bool both = true && false;      // false (AND — both must be true)
bool either = true || false;    // true  (OR — at least one true)
bool not = !true;               // false (NOT — flips the value)

// Comparison operators (these return bool)
int a = 10, b = 20;
bool equal = a == b;            // false
bool notEqual = a != b;         // true
bool greater = a > b;           // false
bool less = a < b;              // true
bool greaterOrEqual = a >= b;   // false
bool lessOrEqual = a <= b;      // true
```

#### 4.4 Lists: `List<T>`

A list is an ordered collection of items.

```dart
// Creating lists
List<String> fruits = ['Apple', 'Banana', 'Mango'];
List<int> numbers = [1, 2, 3, 4, 5];
var mixed = [1, 'hello', true];  // List<Object>

// Accessing items (index starts at 0)
print(fruits[0]);     // 'Apple' (first item)
print(fruits[1]);     // 'Banana'
print(fruits[2]);     // 'Mango'
// print(fruits[3]);  // ERROR! Index out of bounds

// List properties
print(fruits.length);   // 3
print(fruits.isEmpty);  // false
print(fruits.isNotEmpty); // true
print(fruits.first);    // 'Apple'
print(fruits.last);     // 'Mango'

// Adding items
fruits.add('Orange');          // ['Apple', 'Banana', 'Mango', 'Orange']
fruits.insert(1, 'Grape');     // ['Apple', 'Grape', 'Banana', 'Mango', 'Orange']

// Removing items
fruits.remove('Banana');       // Removes by value
fruits.removeAt(0);            // Removes at index
fruits.removeLast();           // Removes last item
fruits.clear();                // Removes everything

// Checking existence
print(fruits.contains('Apple'));  // true/false
print(fruits.indexOf('Apple'));   // Index or -1 if not found

// Looping
for (var fruit in fruits) {
  print(fruit);
}

fruits.forEach((fruit) => print(fruit));
```

#### 4.5 Maps: `Map<K, V>`

A map stores key-value pairs. Like a dictionary — you look up a word (key) to find its definition (value).

```dart
// Creating maps
Map<String, int> ages = {
  'Alice': 30,
  'Bob': 25,
  'Charlie': 35,
};

Map<String, dynamic> person = {
  'name': 'Alice',
  'age': 30,
  'city': 'New York',
  'isStudent': false,
};

// Accessing values
print(ages['Alice']);       // 30
print(person['name']);      // 'Alice'
print(person['salary']);    // null (key doesn't exist)

// Adding/updating
ages['David'] = 28;         // Add new entry
ages['Alice'] = 31;         // Update existing

// Properties
print(ages.length);         // 4
print(ages.keys);           // (Alice, Bob, Charlie, David)
print(ages.values);         // (31, 25, 35, 28)
print(ages.containsKey('Alice')); // true
print(ages.containsValue(25));    // true

// Looping
ages.forEach((name, age) {
  print('$name is $age years old');
});

for (var name in ages.keys) {
  print(name);
}

for (var age in ages.values) {
  print(age);
}
```

**`dynamic` type:** Means "could be any type." Used when you don't know the type in advance.

#### 4.6 Records (Dart 3+)

Records group multiple values into a single object:

```dart
// Positional record
var record = ('Alice', 30, true);
print(record.$1);  // 'Alice'
print(record.$2);  // 30
print(record.$3);  // true

// Named record
var person = (name: 'Alice', age: 30);
print(person.name);  // 'Alice'
print(person.age);   // 30

// Record with types
(String, int) getPerson() {
  return ('Alice', 30);
}
```

---

### Chapter 5: Control Flow — Making Decisions

#### 5.1 If/Else statements

```dart
int age = 18;

if (age >= 18) {
  print('Adult');
} else {
  print('Minor');
}

// Multiple conditions
int score = 85;

if (score >= 90) {
  print('A');
} else if (score >= 80) {
  print('B');
} else if (score >= 70) {
  print('C');
} else {
  print('F');
}

// Combining conditions
bool hasLicense = true;
int driverAge = 20;

if (driverAge >= 18 && hasLicense) {
  print('Can drive');
} else {
  print('Cannot drive');
}
```

#### 5.2 Ternary operator (shorthand if/else)

```dart
// Long way:
String status;
if (age >= 18) {
  status = 'Adult';
} else {
  status = 'Minor';
}

// Short way (ternary):
String status = age >= 18 ? 'Adult' : 'Minor';
```

#### 5.3 Switch statements

```dart
String grade = 'A';

switch (grade) {
  case 'A':
    print('Excellent!');
    break;
  case 'B':
    print('Good');
    break;
  case 'C':
    print('Average');
    break;
  case 'D':
  case 'F':
    print('Needs improvement');
    break;
  default:
    print('Invalid grade');
}

// Modern switch (Dart 3+)
switch (grade) {
  case 'A' => print('Excellent!');
  case 'B' => print('Good');
  case 'C' => print('Average');
  case 'D' || 'F' => print('Needs improvement');
  _ => print('Invalid grade');
}
```

#### 5.4 For loops

```dart
// Traditional for loop
for (int i = 0; i < 5; i++) {
  print('Count: $i');  // 0, 1, 2, 3, 4
}

// For-in loop (with lists)
List<String> names = ['Alice', 'Bob', 'Charlie'];
for (var name in names) {
  print(name);
}

// For-each
names.forEach((name) => print(name));

// For loop with index
for (int i = 0; i < names.length; i++) {
  print('$i: ${names[i]}');
}
```

#### 5.5 While loops

```dart
int count = 0;
while (count < 5) {
  print(count);
  count++;
}

// Do-while (runs at least once)
int i = 0;
do {
  print(i);
  i++;
} while (i < 5);
```

#### 5.6 Break and Continue

```dart
// Break — exit loop immediately
for (int i = 0; i < 10; i++) {
  if (i == 5) break;  // Stop at 5
  print(i);  // 0, 1, 2, 3, 4
}

// Continue — skip to next iteration
for (int i = 0; i < 10; i++) {
  if (i % 2 == 0) continue;  // Skip even numbers
  print(i);  // 1, 3, 5, 7, 9
}
```

---

### Chapter 6: Functions — Reusable Code Blocks

#### 6.1 What is a function?

A function is a named block of code that does ONE specific thing.

```dart
// Function that prints a greeting
void sayHello() {
  print('Hello!');
}

// Using (calling) the function
sayHello();  // Prints: Hello!
```

#### 6.2 Parts of a function

```dart
ReturnType functionName(parameters) {
  // body
  return value;
}
```

| Part | Meaning | Example |
|------|---------|---------|
| `ReturnType` | What the function gives back | `void` (nothing), `int`, `String`, `bool` |
| `functionName` | How to call it | `add`, `greet`, `calculateTotal` |
| `parameters` | Inputs it needs | `(int a, int b)` |
| `body` | What it does | `{ return a + b; }` |
| `return` | Output the result | `return result;` |

#### 6.3 Functions with parameters

```dart
// Function with two parameters
int add(int a, int b) {
  return a + b;
}

// Using it
int sum = add(3, 4);  // sum = 7
print(sum);            // 7
```

#### 6.4 Functions with named parameters

Named parameters use curly braces and are optional by default:

```dart
void greet({required String name, int age = 0}) {
  print('Hello $name!');
  if (age > 0) {
    print('You are $age years old');
  }
}

// Using it
greet(name: 'Alice');           // Hello Alice!
greet(name: 'Bob', age: 25);    // Hello Bob! You are 25 years old
// greet('Alice');              // ERROR! must use name:
```

**`required`** means you MUST provide this parameter.  
**`= 0`** is a default value (if not provided, it's 0).

#### 6.5 Arrow functions (shorthand)

When a function body is a single expression, use `=>`:

```dart
// Long way
int add(int a, int b) {
  return a + b;
}

// Short way (arrow)
int add(int a, int b) => a + b;

// Another example
bool isEven(int n) => n % 2 == 0;
String greet(String name) => 'Hello, $name!';
void printSum(int a, int b) => print(a + b);
```

#### 6.6 Functions as values

In Dart, functions are **first-class citizens** — you can pass them around like variables:

```dart
// Assign function to variable
int add(int a, int b) => a + b;
var myFunction = add;
print(myFunction(3, 4));  // 7

// Pass function as parameter
void execute(int Function(int, int) operation, int a, int b) {
  print(operation(a, b));
}

execute(add, 3, 4);  // 7
execute((a, b) => a * b, 3, 4);  // 12

// Anonymous functions (lambdas)
[1, 2, 3].forEach((n) {
  print(n * 2);
});

// Arrow lambda
[1, 2, 3].map((n) => n * 2).toList();  // [2, 4, 6]
```

---

### Chapter 7: Collections Operations (Critical for Flutter)

These are used constantly in Flutter development. **Memorize them.**

#### 7.1 `.map()` — Transform each item

```dart
List<int> numbers = [1, 2, 3, 4, 5];

// Double every number
List<int> doubled = numbers.map((n) => n * 2).toList();
// Result: [2, 4, 6, 8, 10]

// Convert to strings
List<String> strings = numbers.map((n) => 'Number $n').toList();
// Result: ['Number 1', 'Number 2', 'Number 3', 'Number 4', 'Number 5']

// With objects
List<User> users = [User('Alice'), User('Bob')];
List<String> names = users.map((u) => u.name).toList();
// Result: ['Alice', 'Bob']
```

**Common mistake:** Forgetting `.toList()`. Without it, `.map()` returns a lazy Iterable, not a List.

#### 7.2 `.where()` — Filter items

```dart
List<int> numbers = [1, 2, 3, 4, 5, 6];

// Get even numbers
List<int> evens = numbers.where((n) => n.isEven).toList();
// Result: [2, 4, 6]

// Get numbers greater than 3
List<int> big = numbers.where((n) => n > 3).toList();
// Result: [4, 5, 6]

// With objects
List<User> adults = users.where((u) => u.age >= 18).toList();
```

#### 7.3 `.firstWhere()` — Find first match

```dart
List<int> numbers = [1, 2, 3, 4, 5];

int firstEven = numbers.firstWhere((n) => n.isEven);
// Result: 2

int firstBig = numbers.firstWhere(
  (n) => n > 10,
  orElse: () => -1,  // Return -1 if no match
);
// Result: -1
```

#### 7.4 `.any()` and `.every()` — Check conditions

```dart
List<int> numbers = [1, 2, 3, 4, 5];

bool hasEven = numbers.any((n) => n.isEven);       // true (at least one even)
bool allEven = numbers.every((n) => n.isEven);     // false (not all even)
bool allPositive = numbers.every((n) => n > 0);    // true

// Real-world example:
bool hasOutstanding = orders.any((o) => !o.paid);
bool allDelivered = orders.every((o) => o.status == 'delivered');
```

#### 7.5 `.fold()` — Combine into one value

```dart
List<int> numbers = [1, 2, 3, 4, 5];

int sum = numbers.fold(0, (total, n) => total + n);
// Result: 15 (0+1+2+3+4+5)

int product = numbers.fold(1, (total, n) => total * n);
// Result: 120 (1 × 1 × 2 × 3 × 4 × 5)

String combined = ['a', 'b', 'c'].fold('', (str, c) => str + c);
// Result: 'abc'

// Real-world: total sales
int totalSales = orders.fold(0, (sum, order) => sum + order.amount);
```

#### 7.6 `.sort()` — Sort lists

```dart
List<int> numbers = [3, 1, 4, 1, 5, 9];
numbers.sort();
// Result: [1, 1, 3, 4, 5, 9]

// Descending
numbers.sort((a, b) => b.compareTo(a));
// Result: [9, 5, 4, 3, 1, 1]

// With objects
users.sort((a, b) => a.name.compareTo(b.name));   // Alphabetical
users.sort((a, b) => b.age.compareTo(a.age));      // By age descending
```

#### 7.7 Spread operator `...`

```dart
// With lists
var a = [1, 2, 3];
var b = [0, ...a, 4];     // [0, 1, 2, 3, 4]
var c = [0, ...?a, 4];    // Same but safe if a is null (null-aware spread)

// With maps
var original = {'name': 'Alice', 'age': 30};
var updated = {...original, 'city': 'NYC'};
// {'name': 'Alice', 'age': 30, 'city': 'NYC'}
```

#### 7.8 `.toList()` — ALWAYS remember this

```dart
var result = [1, 2, 3].map((n) => n * 2);
print(result.runtimeType);  // MappedListIterable<int, int> (NOT a List!)
print(result.length);        // ERROR! No .length on Iterable

var list = result.toList();
print(list.runtimeType);     // List<int>
print(list.length);           // 3
```

---

### Chapter 8: Classes — Creating Your Own Types

#### 8.1 What is a class?

A **class** is a blueprint for creating objects.

```dart
// Blueprint for a Person
class Person {
  String name;   // Fields (what a Person has)
  int age;

  Person(this.name, this.age);  // Constructor (how to create)

  void introduce() {            // Methods (what a Person can do)
    print('Hi, I am $name and I am $age');
  }
}

// Create actual people (objects)
var alice = Person('Alice', 30);
var bob = Person('Bob', 25);

alice.introduce();  // Hi, I am Alice and I am 30
bob.introduce();    // Hi, I am Bob and I am 25
```

#### 8.2 Constructor types

```dart
// Positional constructor
class Point {
  int x, y;
  Point(this.x, this.y);  // Positional: Point(3, 4)
}

// Named constructor with required
class User {
  String name;
  int age;
  User({required this.name, required this.age});  // User(name: 'Alice', age: 30)
}

// Named constructor with defaults
class Settings {
  bool darkMode;
  String language;
  Settings({this.darkMode = false, this.language = 'en'});
  // Settings() → darkMode=false, language='en'
  // Settings(darkMode: true) → darkMode=true, language='en'
}

// Multiple constructors
class Color {
  int r, g, b;
  
  Color(this.r, this.g, this.b);           // Primary: Color(255, 0, 0)
