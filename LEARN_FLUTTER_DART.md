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
// Result: 120 (1*1*2*3*4*5)

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
  
  Color.red() : this(255, 0, 0);            // Named: Color.red()
  Color.green() : this(0, 255, 0);          // Named: Color.green()
  Color.fromHex(String hex) : /* parse */ this(0, 0, 0);
}
```

#### 8.3 Immutability with `final`

For state management (Riverpod), we make fields `final`:

```dart
class Todo {
  final int id;          // Can never change after construction
  final String title;
  final bool isDone;

  const Todo({
    required this.id,
    required this.title,
    this.isDone = false,
  });
}

var todo = Todo(id: 1, title: 'Learn Dart');
// todo.title = 'Learn Flutter';  // ERROR! title is final
```

**But how do we change it?** We create a NEW instance with `copyWith`.

#### 8.4 The `copyWith` method

```dart
class Todo {
  final int id;
  final String title;
  final bool isDone;

  const Todo({
    required this.id,
    required this.title,
    this.isDone = false,
  });

  // Returns a NEW Todo with some fields changed
  Todo copyWith({
    int? id,
    String? title,
    bool? isDone,
  }) {
    return Todo(
      id: id ?? this.id,          // If new id provided, use it; else keep old
      title: title ?? this.title,
      isDone: isDone ?? this.isDone,
    );
  }
}

var original = Todo(id: 1, title: 'Learn Dart');
var updated = original.copyWith(isDone: true);
// original is UNCHANGED
// updated = Todo(id: 1, title: 'Learn Dart', isDone: true)
```

**Why `??`?** Because the parameter is optional. If we don't pass a value, it's null, so `id ?? this.id` means "keep the old id."

#### 8.5 Getters (computed properties)

```dart
class Rectangle {
  final double width;
  final double height;

  Rectangle({required this.width, required this.height});

  // Getter — looks like a field but computes value
  double get area => width * height;
  double get perimeter => 2 * (width + height);
  bool get isSquare => width == height;
}

var rect = Rectangle(width: 5, height: 3);
print(rect.area);        // 15.0
print(rect.perimeter);   // 16.0
print(rect.isSquare);    // false
```

**Getters vs methods:**
- Getter: `get area` → `rect.area` (no parentheses)
- Method: `double area()` → `rect.area()` (with parentheses)
- Use getters for properties that feel like fields

#### 8.6 Static members

Belong to the class itself, not to instances:

```dart
class MathUtils {
  static const double pi = 3.14159;

  static int add(int a, int b) => a + b;

  static double circleArea(double radius) => pi * radius * radius;
}

// Use without creating an instance:
print(MathUtils.pi);        // 3.14159
print(MathUtils.add(3, 4)); // 7
print(MathUtils.circleArea(5)); // 78.53975
```

---

### Chapter 9: Enums — Fixed Set of Values

#### 9.1 What is an enum?

An enum defines a limited set of named values:

```dart
enum Day { monday, tuesday, wednesday, thursday, friday, saturday, sunday }

enum Status { pending, approved, rejected }

enum OrderStatus { placed, confirmed, preparing, outForDelivery, delivered }
```

#### 9.2 Using enums

```dart
enum Color { red, green, blue }

Color selectedColor = Color.red;

print(selectedColor.name);   // 'red' (as a string)
print(selectedColor.index);  // 0 (position in the enum)

// Switch (must handle ALL values!)
switch (selectedColor) {
  case Color.red:   print('Red selected'); break;
  case Color.green: print('Green selected'); break;
  case Color.blue:  print('Blue selected'); break;
}

// Iterate all values
for (var color in Color.values) {
  print(color.name);
}
```

#### 9.3 Enums with properties (enhanced enums)

```dart
enum Status {
  pending('Pending', 0),
  approved('Approved', 1),
  rejected('Rejected', -1);

  final String label;
  final int code;
  const Status(this.label, this.code);
}

print(Status.approved.label);  // 'Approved'
print(Status.approved.code);   // 1
```

---

### Chapter 10: Async/Await — Handling Time

#### 10.1 What is async code?

Some operations take time:
- Loading a file from disk
- Fetching data from the internet
- Reading from a database
- Waiting for a timer

If the app waited for these to finish, the screen would freeze. **Async code** lets the app do other work while waiting.

**Analogy:** You order food at a restaurant. Instead of standing at the counter staring at the cook (synchronous), you sit at your table and scroll your phone (async). When the food is ready, they call you.

#### 10.2 What is a Future?

A `Future<T>` represents a value that will be available **later**.

```dart
Future<String> fetchUserData() {
  // This function returns immediately, but the String comes later
  return Future.delayed(Duration(seconds: 2), () => 'User data loaded');
}

void main() {
  print('Start');
  var result = fetchUserData();
  print(result);  // Instance of 'Future<String>' (NOT the string!)
  print('End');
}
// Output:
// Start
// Instance of 'Future<String>'
// End
// (2 seconds later... the Future completes, but nothing printed it)
```

| Term | Meaning |
|------|---------|
| `Future` | A promise that a value will arrive later |
| `Future<String>` | A future that will eventually give you a String |
| `Future.delayed()` | Creates a future that completes after a delay |
| `Future.error()` | A future that completes with an error |

#### 10.3 `async` and `await` — The key to readable async code

```dart
// ❌ Without async/await — hard to read and chain
void main() {
  print('Loading...');
  fetchUserData().then((data) {
    print(data);
  }).catchError((e) {
    print('Error: $e');
  });
}

// ✅ With async/await — looks like normal code
void main() async {
  print('Loading...');
  try {
    String data = await fetchUserData();
    print(data);
  } catch (e) {
    print('Error: $e');
  }
}
```

**Rules:**
- `await` can only be used inside an `async` function
- `async` marks the function as asynchronous (returns a Future)
- `await` pauses the function until the Future completes
- During `await`, other code can run (the app doesn't freeze)

#### 10.4 `async` functions always return Futures

```dart
// Without async — returns String directly
String greet() => 'Hello';

// With async — returns Future<String>
Future<String> greetAsync() async {
  return 'Hello';  // Wrapped in Future automatically
}

void main() async {
  String normal = greet();
  Future<String> future = greetAsync();
  String awaited = await greetAsync();  // Unwrap: 'Hello'
}
```

**Key insight:** If a function is `async`, even if it just returns a simple value, the caller must `await` it.

#### 10.5 Try/Catch/Finally — Handling errors

```dart
Future<String> fetchData() async {
  // Simulate network call
  await Future.delayed(Duration(seconds: 1));
  throw Exception('Network error');
}

void main() async {
  try {
    String data = await fetchData();
    print('Success: $data');
  } catch (e) {
    print('Error happened: $e');
  } finally {
    print('This always runs (success or failure)');
  }
}

// Catching specific types
try {
  await riskyOperation();
} on TimeoutException {
  print('Request timed out');
} on HttpException {
  print('HTTP error');
} catch (e) {
  print('Unknown error: $e');
}
```

#### 10.6 Running multiple futures in parallel

```dart
// Sequential (slow) — each waits for the previous
void main() async {
  var a = await fetchFromApi1();  // 2 seconds
  var b = await fetchFromApi2();  // 2 seconds
  var c = await fetchFromApi3();  // 2 seconds
  // Total: 6 seconds
}

// Parallel (fast) — all run at the same time
void main() async {
  var results = await Future.wait([
    fetchFromApi1(),  // 2 seconds
    fetchFromApi2(),  // 2 seconds
    fetchFromApi3(),  // 2 seconds
  ]);
  // Total: ~2 seconds (all finish together)
  var a = results[0];
  var b = results[1];
  var c = results[2];
}
```

**When to use parallel:**
- Independent API calls (user data AND settings AND notifications)
- Loading multiple files at once
- Processing multiple images

**When NOT to use parallel:**
- One call depends on another (get userId first, THEN get orders)

#### 10.7 `Future.delayed` and `Future.value`

```dart
// Create a future that completes after 3 seconds
Future<String> delayedGreeting() {
  return Future.delayed(Duration(seconds: 3), () => 'Hello after delay');
}

// Create a future that completes immediately with a value
Future<int> immediateValue() {
  return Future.value(42);
}

// Create a future that fails immediately
Future<void> immediateError() {
  return Future.error('Something went wrong');
}
```

#### 10.8 `FutureBuilder` — Using futures in Flutter widgets

```dart
class UserProfile extends StatelessWidget {
  final Future<String> userFuture = fetchUserName();

  @override
  Widget build(BuildContext context) {
    return FutureBuilder<String>(
      future: userFuture,
      builder: (context, snapshot) {
        // snapshot has: connectionState, data, error

        if (snapshot.connectionState == ConnectionState.waiting) {
          return CircularProgressIndicator();  // Loading
        }

        if (snapshot.hasError) {
          return Text('Error: ${snapshot.error}');  // Error
        }

        return Text('Hello, ${snapshot.data}!');  // Success
      },
    );
  }
}
```

| `snapshot` property | Meaning |
|---------------------|---------|
| `connectionState` | `waiting` (loading) or `done` (finished) |
| `hasData` | True if data is available |
| `data` | The value (type T) |
| `hasError` | True if an error occurred |
| `error` | The error object |

**Important:** `future` in FutureBuilder should NOT change on every rebuild. Create it once (e.g., in `initState` or as a top-level variable), not inside `build()`.

#### 10.9 Streams — Multiple values over time

A `Future` gives one value once. A `Stream` gives multiple values over time.

```dart
// Create a stream that emits numbers every second
Stream<int> countStream() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(Duration(seconds: 1));
    yield i;  // "yield" emits a value (like "return" but multiple times)
  }
}

// Listen to the stream
void main() async {
  await for (var number in countStream()) {
    print(number);  // 1, 2, 3, 4, 5 (one per second)
  }
  print('Done!');
}
```

**Stream subscription:**
```dart
Stream<int> stream = countStream();
var subscription = stream.listen(
  (data) => print('Got: $data'),   // onData
  onError: (e) => print('Error: $e'),  // onError
  onDone: () => print('Stream finished'),  // onDone
);

// Cancel when no longer needed (e.g., in dispose)
subscription.cancel();
```

#### 10.10 `StreamBuilder` — Using streams in Flutter

```dart
class TimerWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return StreamBuilder<int>(
      stream: countStream(),
      builder: (context, snapshot) {
        if (snapshot.hasError) {
          return Text('Error: ${snapshot.error}');
        }

        if (!snapshot.hasData) {
          return Text('Waiting...');
        }

        return Text('Count: ${snapshot.data}');
      },
    );
  }
}
```

#### 10.11 Common async mistakes

```dart
// ❌ Forgetting await — prints Future, not value
void printUser() {
  var name = fetchUserName();  // Returns Future<String>
  print(name);  // Instance of 'Future<String>'
}

// ✅ Correct
void printUser() async {
  var name = await fetchUserName();
  print(name);
}

// ❌ async function without await — unnecessary
Future<void> doSomething() async {
  print('Hello');
}

// ✅ Only use async if you actually await something
void doSomething() {
  print('Hello');
}
```

#### 10.12 Practice exercises

**Exercise 1:** Create a function that simulates checking user login. If username is 'admin' and password is '1234', return 'Login successful' after 1 second. Otherwise, throw an error.

```dart
Future<String> login(String username, String password) async {
  await Future.delayed(Duration(seconds: 1));
  if (username == 'admin' && password == '1234') {
    return 'Login successful';
  }
  throw Exception('Invalid credentials');
}

void main() async {
  try {
    var result = await login('admin', '1234');
    print(result);  // Login successful
  } catch (e) {
    print(e);
  }
}
```

**Exercise 2:** Fetch two independent pieces of data in parallel.

```dart
Future<String> fetchUserName() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Alice';
}

Future<int> fetchUserAge() async {
  await Future.delayed(Duration(seconds: 2));
  return 30;
}

void main() async {
  var results = await Future.wait([fetchUserName(), fetchUserAge()]);
  print('Name: ${results[0]}, Age: ${results[1]}');
  // Total: ~2 seconds (not 4)
}
```

**Exercise 3:** Use FutureBuilder to show loading, error, and success states.

```dart
class WeatherWidget extends StatelessWidget {
  final Future<String> weatherFuture;

  const WeatherWidget({required this.weatherFuture});

  @override
  Widget build(BuildContext context) {
    return FutureBuilder<String>(
      future: weatherFuture,
      builder: (context, snapshot) {
        if (snapshot.connectionState == ConnectionState.waiting) {
          return Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              CircularProgressIndicator(),
              SizedBox(height: 16),
              Text('Fetching weather...'),
            ],
          );
        }

        if (snapshot.hasError) {
          return Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Icon(Icons.error, color: Colors.red, size: 48),
              SizedBox(height: 16),
              Text('Could not load weather'),
            ],
          );
        }

        return Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(Icons.sunny, size: 64, color: Colors.orange),
            SizedBox(height: 16),
            Text(snapshot.data!, style: TextStyle(fontSize: 24)),
          ],
        );
      },
    );
  }
}
```

---

### Chapter 11: Advanced Dart — Generics, Extensions & More

#### 11.1 Generics — Type Parameters

**What is a generic?** A way to write code that works with ANY type, not just one specific type.

**Analogy:** A box that can hold anything. You decide what goes in when you create it.

```dart
// Without generics — must write separate code for each type
class StringBox { String value; StringBox(this.value); }
class IntBox { int value; IntBox(this.value); }
class DoubleBox { double value; DoubleBox(this.value); }

// With generics — ONE class works for ALL types
class Box<T> {        // T = "placeholder type"
  T value;
  Box(this.value);
}

void main() {
  var stringBox = Box<String>('Hello');  // T = String
  var intBox = Box<int>(42);             // T = int
  var doubleBox = Box<double>(3.14);     // T = double

  print(stringBox.value);  // 'Hello'
  print(intBox.value);     // 42
}
```

**Why generics matter:**
```dart
// Without generics — UNSAFE (can put anything in)
List names = ['Alice', 'Bob'];
names.add(42);  // Oops! Mixed types — crashes later

// With generics — SAFE (compiler checks types)
List<String> names = ['Alice', 'Bob'];
names.add('Charlie');  // OK
names.add(42);          // ERROR! Can't put int into List<String>
```

**Generic functions:**
```dart
// Works with any type T
T firstOrNull<T>(List<T> items) {
  if (items.isEmpty) return null as T;  // null for any type
  return items.first;
}

void main() {
  int? firstInt = firstOrNull<int>([1, 2, 3]);     // 1
  String? firstStr = firstOrNull<String>([]);       // null
}

// Type can often be inferred:
var first = firstOrNull([1, 2, 3]);  // Dart infers T = int
```

**Generic constraints — restrict what types are allowed:**
```dart
// T must be a subtype of num (int or double)
T sumList<T extends num>(List<T> items) {
  return items.fold(0 as T, (a, b) => (a + b) as T);
}

void main() {
  print(sumList<int>([1, 2, 3]));       // 6
  print(sumList<double>([1.5, 2.5]));   // 4.0
  // sumList<String>(['a', 'b']);       // ERROR! String doesn't extend num
}
```

**Generics with Riverpod (you've been using them!):**
```dart
// Notifier<CounterState> — T is replaced by CounterState
class CounterNotifier extends Notifier<CounterState> { ... }

// NotifierProvider<CounterNotifier, CounterState> — two type parameters
final counterProvider = NotifierProvider<CounterNotifier, CounterState>(...);

// State class with generic — works with any data type
class DataState<T> {
  final bool loading;
  final T? data;
  final String? error;
  // ...
}
```

#### 11.2 Extensions — Adding Methods to Existing Types

**What is an extension?** Adds new methods to a type you DON'T own (like String, int, or a class from a package).

**Analogy:** You can't modify the String class (it's in Dart core), but you can "extend" it with new abilities.

```dart
// Add methods to String
extension StringExtensions on String {
  // Capitalize first letter
  String get capitalized =>
    this.isEmpty ? this : this[0].toUpperCase() + substring(1);

  // Check if valid email (simple version)
  bool get isValidEmail => contains('@') && contains('.');

  // Count words in a string
  int get wordCount => trim().isEmpty ? 0 : trim().split(/\s+/).length;

  // Reverse the string
  String get reversed => split('').reversed.join();
}

void main() {
  print('hello'.capitalized);      // 'Hello'
  print('alice@email.com'.isValidEmail); // true
  print('hello world'.wordCount);  // 2
  print('dart'.reversed);          // 'trad'
}
```

**Extensions on generic types:**
```dart
extension ListExtensions<T> on List<T> {
  // Get second element (safe)
  T? get second => length > 1 ? this[1] : null;

  // Get last n elements
  List<T> lastN(int n) => sublist(length - n.clamp(0, length));

  // Shuffle and return new list
  List<T> shuffled() => toList()..shuffle();
}

void main() {
  var nums = [1, 2, 3, 4, 5];
  print(nums.second);       // 2
  print(nums.lastN(3));     // [3, 4, 5]
  print(nums.shuffled());   // [3, 1, 5, 2, 4]
}
```

**Real-world use case — context extensions:**
```dart
// Very common Flutter pattern
extension BuildContextExtensions on BuildContext {
  ThemeData get theme => Theme.of(this);
  TextTheme get textTheme => theme.textTheme;
  MediaQueryData get mediaQuery => MediaQuery.of(this);
  double get screenWidth => mediaQuery.size.width;
  double get screenHeight => mediaQuery.size.height;
  bool get isDarkMode => theme.brightness == Brightness.dark;

  void showSnackBar(String message) {
    ScaffoldMessenger.of(this).showSnackBar(
      SnackBar(content: Text(message)),
    );
  }
}

// Usage in any widget:
@override
Widget build(BuildContext context) {
  if (context.isDarkMode) { ... }
  print(context.screenWidth);
  context.showSnackBar('Hello!');
}
```

**Extension on enums (very useful):**
```dart
enum Status { pending, approved, rejected }

extension StatusExtension on Status {
  String get label {
    switch (this) {
      case Status.pending: return 'Pending';
      case Status.approved: return 'Approved';
      case Status.rejected: return 'Rejected';
    }
  }

  Color get color {
    switch (this) {
      case Status.pending: return Colors.orange;
      case Status.approved: return Colors.green;
      case Status.rejected: return Colors.red;
    }
  }
}

// Usage:
Container(
  color: order.status.color,
  child: Text(order.status.label),
)
```

#### 11.3 Mixins — Reusable Behaviors

**What is a mixin?** A chunk of reusable code that can be "mixed into" multiple classes. Like a recipe you can add to any dish.

**Analogy:** A car has features (GPS, Bluetooth, Heated seats). Each feature is a mixin — you can add it to any car model without changing the car's core design.

```dart
// Define a mixin
mixin Logger {
  void log(String message) {
    print('[LOG]: $message');
  }
}

mixin Validator {
  bool isValidEmail(String email) => email.contains('@');
  bool isNotEmpty(String value) => value.trim().isNotEmpty;
}

// Use mixins with 'with' keyword
class AuthService with Logger, Validator {
  void login(String email, String password) {
    log('Attempting login...');
    if (!isValidEmail(email)) {
      log('Invalid email');
      return;
    }
    // ... login logic
  }
}

class TodoService with Logger {
  void addTodo(String title) {
    log('Adding todo: $title');
    // ...
  }
}

void main() {
  var auth = AuthService();
  auth.login('test@email.com', '123');  // Logs: Attempting login...

  var todos = TodoService();
  todos.addTodo('Learn Dart');  // Logs: Adding todo: Learn Dart
}
```

**Mixins vs Inheritance:**
```dart
// Inheritance — "is a" relationship
// A Dog IS-AN Animal
class Animal { void breathe() => print('breathing'); }
class Dog extends Animal { void bark() => print('bark'); }

// Mixin — "has a" capability
// A Dog CAN Fly? No. A Bird CAN Fly.
mixin Flyable {
  void fly() => print('flying');
}

class Bird extends Animal with Flyable { }
class Airplane with Flyable { }  // Not an animal, but can fly!

// Multiple mixins
class SuperBird extends Animal with Flyable, Swimmable, Runnable { }
```

**Real-world Flutter mixins:**
```dart
// Flutter uses mixins extensively
class _MyState extends State<MyWidget> with TickerProviderStateMixin {
  // TickerProviderStateMixin gives us the ability to create AnimationControllers
  late AnimationController _controller;
}

// Riverpod mixins:
class MyNotifier extends Notifier<MyState> {
  // Notifier itself gives us 'state' property and 'build()' requirement
}

// Your own mixin for loading states:
mixin LoadingMixin<T extends Notifier> on T {
  bool _loading = false;
  bool get isLoading => _loading;

  Future<T> runWithLoading<T>(Future<T> Function() action) async {
    _loading = true;
    try {
      return await action();
    } finally {
      _loading = false;
    }
  }
}
```

#### 11.4 Sets — Unique Collections

```dart
// A Set is like a List, but each value appears only ONCE
Set<String> fruits = {'Apple', 'Banana', 'Apple', 'Mango'};
print(fruits);  // {Apple, Banana, Mango} — no duplicates!

// When to use Sets vs Lists:
// List — ordered, allows duplicates, access by index
// Set — unordered, no duplicates, fast "contains" check

var names = ['Alice', 'Bob', 'Alice'];  // List — Alice appears twice
var uniqueNames = {'Alice', 'Bob', 'Alice'};  // Set — Alice once

// Common Set operations:
Set<int> a = {1, 2, 3, 4, 5};
Set<int> b = {4, 5, 6, 7, 8};

Set<int> union = a.union(b);        // {1, 2, 3, 4, 5, 6, 7, 8}
Set<int> intersection = a.intersection(b);   // {4, 5}
Set<int> difference = a.difference(b);       // {1, 2, 3}

// Real-world use: unique tags
List<String> allTags = ['dart', 'flutter', 'dart', 'firebase', 'flutter'];
Set<String> uniqueTags = allTags.toSet();  // {dart, flutter, firebase}

// Fast lookup:
Set<String> adminEmails = {'admin@company.com', 'boss@company.com'};
if (adminEmails.contains(email)) { ... }  // O(1) — instant!
```

#### 11.5 Exception Handling Deep Dive

```dart
// Try/Catch — catch ANY error
try {
  await http.get(...);
} catch (e) {
  print('Something went wrong: $e');
}

// Catch specific types
try {
  await http.get(...);
} on SocketException {
  print('No internet connection');
} on TimeoutException {
  print('Request timed out');
} catch (e) {
  print('Other error: $e');
}

// Finally — always runs (for cleanup)
var file = File('data.txt');
try {
  await file.writeAsString('Hello');
} catch (e) {
  print('Write failed: $e');
} finally {
  await file.close();  // Always close the file!
}

// Custom exceptions
class NetworkException implements Exception {
  final String message;
  final int statusCode;

  NetworkException(this.message, this.statusCode);

  @override
  String toString() => 'NetworkException($statusCode): $message';
}

// Throw it
throw NetworkException('User not found', 404);

// Catch it
try {
  await api.getUser(42);
} on NetworkException catch (e) {
  if (e.statusCode == 404) {
    print('User does not exist');
  } else if (e.statusCode == 500) {
    print('Server error, try again later');
  }
}

// Re-throw (catch, log, then pass up)
try {
  await riskyOperation();
} catch (e) {
  logError(e);  // Log locally
  rethrow;      // Let the caller handle it too
}
```

#### 11.6 Factory Constructors

```dart
// A factory constructor doesn't always create a NEW instance.
// It can return an existing instance or a subtype.

class DatabaseConnection {
  static final Map<String, DatabaseConnection> _cache = {};

  final String url;

  // Private constructor — can't call from outside
  DatabaseConnection._(this.url);

  // Factory constructor — returns cached or creates new
  factory DatabaseConnection(String url) {
    if (_cache.containsKey(url)) {
      return _cache[url]!;  // Return existing connection
    }
    final conn = DatabaseConnection._(url);
    _cache[url] = conn;     // Cache it
    return conn;
  }
}

// Both variables point to the SAME object
var conn1 = DatabaseConnection('localhost');
var conn2 = DatabaseConnection('localhost');
print(conn1 == conn2);  // true (same cached instance)

// Factory with JSON parsing (common pattern):
class User {
  final String name;
  final int age;

  User({required this.name, required this.age});

  // Factory constructors for JSON are common:
  factory User.fromJson(Map<String, dynamic> json) {
    return User(
      name: json['name'] as String,
      age: json['age'] as int,
    );
  }
}
```

#### 11.7 Exercise: Build a reusable data layer

Use generics, extensions, and mixins to build a reusable local storage service:

```dart
// 1. Generic repository interface
mixin StorageMixin<T> {
  Future<List<T>> loadAll();
  Future<void> saveAll(List<T> items);
}

// 2. Extension on List for JSON conversion
extension JsonListExtension<T> on List<T> {
  List<Map<String, dynamic>> toJsonList(
    Map<String, dynamic> Function(T) toJson,
  ) => map((item) => toJson(item)).toList();
}

// 3. Concrete implementation
class TodoStorage with StorageMixin<TodoModel> {
  @override
  Future<List<TodoModel>> loadAll() async {
    final file = await _getFile();
    if (!await file.exists()) return [];
    final json = await file.readAsString();
    return (jsonDecode(json) as List)
      .map((j) => TodoModel.fromJson(j))
      .toList();
  }

  @override
  Future<void> saveAll(List<TodoModel> items) async {
    final file = await _getFile();
    await file.writeAsString(
      jsonEncode(items.toJsonList((t) => t.toJson())),
    );
  }

  Future<File> _getFile() async {
    final dir = await getApplicationDocumentsDirectory();
    return File('${dir.path}/todos.json');
  }
}
```

---

### Chapter 12: Theming & Dark Mode — Making Your App Beautiful

#### 12.1 What is theming?

Theming is defining a consistent visual style for your app: colors, fonts, spacing, shapes. Instead of setting each button's color individually, you set it ONCE in the theme.

**Without theming — every widget has individual colors:**
```dart
ElevatedButton(
  style: ElevatedButton.styleFrom(
    backgroundColor: Color(0xFF2196F3),
    foregroundColor: Colors.white,
    shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(8)),
  ),
  child: Text('Submit'),
)
```

**With theming — colors come from ONE central place:**
```dart
// The button automatically uses theme colors
ElevatedButton(
  onPressed: () {},
  child: Text('Submit'),
)
```

#### 12.2 ThemeData — The Central Theme Object

```dart
MaterialApp(
  theme: ThemeData(
    // Color scheme — defines primary, secondary, surface colors
    colorScheme: ColorScheme.fromSeed(
      seedColor: Color(0xFF2196F3),  // Blue — generates a palette
      brightness: Brightness.light,   // Light mode
    ),

    // Typography — font sizes and styles
    textTheme: TextTheme(
      headlineLarge: TextStyle(fontSize: 32, fontWeight: FontWeight.bold),
      headlineMedium: TextStyle(fontSize: 24, fontWeight: FontWeight.w600),
      bodyLarge: TextStyle(fontSize: 16),
      bodyMedium: TextStyle(fontSize: 14),
      labelLarge: TextStyle(fontSize: 14, fontWeight: FontWeight.w500),
    ),

    // Component themes — individual widget defaults
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        padding: EdgeInsets.symmetric(horizontal: 24, vertical: 12),
        shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(12)),
      ),
    ),

    cardTheme: CardThemeData(
      elevation: 2,
      shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(16)),
    ),

    appBarTheme: AppBarTheme(
      centerTitle: true,
      elevation: 0,
    ),

    inputDecorationTheme: InputDecorationTheme(
      border: OutlineInputBorder(borderRadius: BorderRadius.circular(12)),
      filled: true,
    ),

    // Use Material 3 (modern design)
    useMaterial3: true,
  ),
)
```

**How to use theme colors in your widgets:**
```dart
@override
Widget build(BuildContext context) {
  final theme = Theme.of(context);
  final colors = theme.colorScheme;   // Access color scheme
  final textStyle = theme.textTheme;  // Access text styles

  return Container(
    color: colors.primary,              // Main brand color
    child: Column(
      children: [
        Text('Title', style: textStyle.headlineMedium),
        Text('Body text', style: textStyle.bodyLarge?.copyWith(
          color: colors.onPrimary,      // Text color on primary background
        )),
        Card(
          color: colors.surface,         // Card background
          child: Text('Card content', style: textStyle.bodyMedium),
        ),
      ],
    },
  );
}
```

**Color scheme cheat sheet:**
```dart
final c = Theme.of(context).colorScheme;

c.primary;          // Main brand color (buttons, app bar)
c.onPrimary;        // Text/icons ON primary background
c.secondary;        // Accent color (floating buttons, badges)
c.onSecondary;      // Text/icons ON secondary
c.surface;          // Card/dialog backgrounds
c.onSurface;        // Text ON surface
c.background;       // Screen backgrounds
c.onBackground;     // Text ON background
c.error;            // Error/warning color
c.onError;          // Text ON error
c.outline;          // Borders, dividers
```

#### 12.3 Dark Mode

```dart
MaterialApp(
  // Define BOTH light and dark themes
  theme: ThemeData(                    // Light mode
    colorScheme: ColorScheme.fromSeed(
      seedColor: Colors.blue,
      brightness: Brightness.light,
    ),
    useMaterial3: true,
  ),

  darkTheme: ThemeData(               // Dark mode
    colorScheme: ColorScheme.fromSeed(
      seedColor: Colors.blue,
      brightness: Brightness.dark,     // ← Changes everything!
    ),
    useMaterial3: true,
  ),

  themeMode: ThemeMode.system,        // Follows device setting
  // themeMode: ThemeMode.light,      // Always light
  // themeMode: ThemeMode.dark,       // Always dark
)
```

**`ThemeMode.system`** reads the user's phone settings:
- If their phone is in dark mode → app uses `darkTheme`
- If their phone is in light mode → app uses `theme`
- This is the RECOMMENDED setting

**Manually toggle theme (with Riverpod):**
```dart
class ThemeState {
  final ThemeMode mode;
  final Color seedColor;

  const ThemeState({this.mode = ThemeMode.system, this.seedColor = Colors.blue});

  ThemeState copyWith({ThemeMode? mode, Color? seedColor}) =>
    ThemeState(mode: mode ?? this.mode, seedColor: seedColor ?? this.seedColor);
}

class ThemeNotifier extends Notifier<ThemeState> {
  @override
  ThemeState build() {
    // Load saved preference
    return const ThemeState();
  }

  ThemeData get lightTheme => ThemeData(
    colorScheme: ColorScheme.fromSeed(
      seedColor: state.seedColor,
      brightness: Brightness.light,
    ),
    useMaterial3: true,
  );

  ThemeData get darkTheme => ThemeData(
    colorScheme: ColorScheme.fromSeed(
      seedColor: state.seedColor,
      brightness: Brightness.dark,
    ),
    useMaterial3: true,
  );

  void setThemeMode(ThemeMode mode) {
    state = state.copyWith(mode: mode);
  }

  void setSeedColor(Color color) {
    state = state.copyWith(seedColor: color);
  }
}

final themeProvider = NotifierProvider<ThemeNotifier, ThemeState>(
  () => ThemeNotifier(),
);

// In main.dart:
class MyApp extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final themeNotifier = ref.watch(themeProvider.notifier);
    final themeState = ref.watch(themeProvider);

    return MaterialApp(
      theme: themeNotifier.lightTheme,
      darkTheme: themeNotifier.darkTheme,
      themeMode: themeState.mode,
      home: HomeScreen(),
    );
  }
}
```

#### 12.4 Typography — Fonts

```dart
// Using Google Fonts:
// Add to pubspec.yaml: google_fonts: ^6.1.0

import 'package:google_fonts/google_fonts.dart';

MaterialApp(
  theme: ThemeData(
    textTheme: GoogleFonts.poppinsTextTheme(),  // Use Poppins font
    // Or customize per style:
    textTheme: TextTheme(
      headlineLarge: GoogleFonts.poppins(fontSize: 32, fontWeight: FontWeight.bold),
      bodyLarge: GoogleFonts.inter(fontSize: 16),
    ),
  ),
)

// Custom fonts (from asset files):
// 1. Add .ttf files to assets/fonts/
// 2. In pubspec.yaml:
//    fonts:
//      - family: MyFont
//        fonts:
//          - asset: assets/fonts/MyFont-Regular.ttf
//          - asset: assets/fonts/MyFont-Bold.ttf
//            weight: 700
// 3. Use in theme:
TextTheme(
  headlineLarge: TextStyle(fontFamily: 'MyFont', fontSize: 32),
)
```

#### 12.5 Custom Theme Extensions

For custom design system values not covered by ThemeData:

```dart
// 1. Define your custom properties class
class AppCustomTheme {
  final double cardBorderRadius;
  final EdgeInsets cardPadding;
  final double buttonHeight;

  const AppCustomTheme({
    this.cardBorderRadius = 16,
    this.cardPadding = const EdgeInsets.all(16),
    this.buttonHeight = 48,
  });
}

// 2. Create an extension to access it
extension CustomTheme on ThemeData {
  static final _custom = AppCustomTheme();

  AppCustomTheme get custom => _custom;
}

// 3. Usage:
Container(
  padding: Theme.of(context).custom.cardPadding,
  child: Text('...'),
)
```

#### 12.6 Exercise: Build a theme switcher

Create a settings screen where users can:
1. Toggle between Light/Dark/System theme
2. Choose from 4 accent colors (Blue, Green, Red, Purple)
3. The theme changes immediately
4. Save preference to SharedPreferences

```dart
// Settings screen with theme controls
class SettingsScreen extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final themeState = ref.watch(themeProvider);
    final colors = Theme.of(context).colorScheme;

    return Scaffold(
      appBar: AppBar(title: Text('Settings')),
      body: ListView(
        padding: EdgeInsets.all(16),
        children: [
          Text('App Theme', style: Theme.of(context).textTheme.titleMedium),
          SizedBox(height: 8),
          SegmentedButton<ThemeMode>(
            segments: [
              ButtonSegment(value: ThemeMode.light, label: Text('Light')),
              ButtonSegment(value: ThemeMode.system, label: Text('System')),
              ButtonSegment(value: ThemeMode.dark, label: Text('Dark')),
            ],
            selected: {themeState.mode},
            onSelectionChanged: (mode) {
              ref.read(themeProvider.notifier).setThemeMode(mode.first);
            },
          ),
          SizedBox(height: 24),
          Text('Accent Color', style: Theme.of(context).textTheme.titleMedium),
          SizedBox(height: 8),
          Wrap(
            spacing: 12,
            children: [
              Colors.blue, Colors.green, Colors.red, Colors.purple,
              Colors.orange, Colors.teal,
            ].map((color) => GestureDetector(
              onTap: () => ref.read(themeProvider.notifier).setSeedColor(color),
              child: Container(
                width: 48, height: 48,
                decoration: BoxDecoration(
                  color: color,
                  shape: BoxShape.circle,
                  border: themeState.seedColor == color
                    ? Border.all(color: colors.onSurface, width: 3)
                    : null,
                ),
              ),
            )).toList(),
          ),
        ],
      ),
    );
  }
}
```

---

## Volume 2: Flutter Framework

---

### Chapter 13: What is Flutter?

#### 11.1 Flutter philosophy

Flutter is different from other mobile frameworks. Instead of using platform-native components (like Android's TextView or iOS's UILabel), Flutter **paints everything itself**.

This means:
- Your app looks the same on Android and iOS
- No bridge between Dart and native code
- Fast 60fps performance
- Hot reload (see changes instantly)

#### 11.2 Everything is a widget

In Flutter, **everything you see on screen is a widget**:

```
App
└── MaterialApp (the app itself)
    └── Scaffold (page layout)
        ├── AppBar (top bar)
        ├── Body
        │   └── Column
        │       ├── Text ("Hello")
        │       ├── SizedBox (space)
        │       ├── Row
        │       │   ├── Icon (star)
        │       │   └── Text ("5.0")
        │       └── ElevatedButton ("Press me")
        └── BottomNavigationBar
```

Text is a widget. Padding is a widget. Even the app itself is a widget.

#### 11.3 Widget tree

Flutter builds UI by **nesting widgets** inside each other:

```dart
Scaffold(
  body: Center(
    child: Column(
      children: [
        Text('Hello'),
        SizedBox(height: 20),
        ElevatedButton(
          onPressed: () {},
          child: Text('Click'),
        ),
      ],
    ),
  ),
)
```

Every `{` creates a new level of nesting. This is called the **widget tree**.

#### 11.4 StatelessWidget vs StatefulWidget

```dart
// NEVER changes — displays static content
class MyTitle extends StatelessWidget {
  final String text;
  const MyTitle({required this.text, super.key});

  @override
  Widget build(BuildContext context) {
    return Text(text, style: TextStyle(fontSize: 24));
  }
}

// CAN change — has mutable state
class Counter extends StatefulWidget {
  @override
  State<Counter> createState() => _CounterState();
}

class _CounterState extends State<Counter> {
  int _count = 0;

  void _increment() {
    setState(() => _count++);
  }

  @override
  Widget build(BuildContext context) {
    return Column(children: [
      Text('$_count'),
      ElevatedButton(onPressed: _increment, child: Text('+')),
    ]);
  }
}
```

**`setState()` is the magic word.** It tells Flutter: "Something changed, rebuild this widget."

#### 11.5 BuildContext

Every `build()` method receives a `BuildContext`:

```dart
@override
Widget build(BuildContext context) {
  // context = "where am I in the widget tree?"
  // Used to access:
  Theme.of(context);      // App theme (colors, fonts)
  Navigator.of(context);  // Screen navigation
  MediaQuery.of(context); // Screen size, orientation
}
```

---

### Chapter 14: Essential Flutter Widgets

#### 12.1 Layout widgets

**Container** — A box with styling:

```dart
Container(
  padding: EdgeInsets.all(16),          // Space INSIDE the box
  margin: EdgeInsets.symmetric(vertical: 8), // Space OUTSIDE
  decoration: BoxDecoration(
    color: Colors.white,
    borderRadius: BorderRadius.circular(12),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.1),
        blurRadius: 8,
        offset: Offset(0, 2),
      ),
    ],
  ),
  child: Text('Hello'),
)
```

**Row** — Horizontal layout:

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceBetween, // Horizontal spacing
  crossAxisAlignment: CrossAxisAlignment.center,      // Vertical alignment
  children: [
    Icon(Icons.star),
    Text('Rating: 4.5'),
    Text('(120 reviews)'),
  ],
)
```

| MainAxisAlignment | Effect |
|-----------------|--------|
| `start` | Left-aligned (default) |
| `center` | Centered |
| `end` | Right-aligned |
| `spaceBetween` | Evenly spaced, first at start, last at end |
| `spaceAround` | Evenly spaced with half-space at edges |
| `spaceEvenly` | Evenly spaced with full space at edges |

**Column** — Vertical layout:

```dart
Column(
  crossAxisAlignment: CrossAxisAlignment.start,  // Horizontal alignment
  mainAxisAlignment: MainAxisAlignment.center,     // Vertical spacing
  children: [
    Text('Title', style: TextStyle(fontSize: 24)),
    SizedBox(height: 8),
    Text('Description text here'),
    SizedBox(height: 16),
    ElevatedButton(onPressed: () {}, child: Text('Action')),
  ],
)
```

**SizedBox** — Empty space:

```dart
SizedBox(height: 16);   // 16 pixels of vertical space
SizedBox(width: 16);    // 16 pixels of horizontal space
SizedBox.shrink();      // Zero size
SizedBox.expand();      // Fills available space
```

**Expanded** — Take remaining space:

```dart
Row(
  children: [
    Text('Left side'),
    Expanded(child: Text('This takes remaining space')),
    Text('Right side'),
  ],
)
```

**Flexible** — Take remaining space but can shrink:

```dart
Row(
  children: [
    Flexible(flex: 2, child: Text('Takes 2/3 of space')),
    Flexible(flex: 1, child: Text('Takes 1/3 of space')),
  ],
)
```

#### 12.2 Information display widgets

**Text:**

```dart
Text(
  'Hello World',
  style: TextStyle(
    fontSize: 18,
    fontWeight: FontWeight.bold,
    color: Colors.blue,
    fontStyle: FontStyle.italic,
    decoration: TextDecoration.underline,
    letterSpacing: 1.5,
    height: 1.5,  // Line height
  ),
  textAlign: TextAlign.center,
  maxLines: 2,
  overflow: TextOverflow.ellipsis,  // "..." if too long
)
```

**Icon:**

```dart
Icon(
  Icons.favorite,
  color: Colors.red,
  size: 48,
)
```

**Image:**

```dart
// From network
Image.network('https://example.com/image.jpg',
  width: 200,
  height: 200,
  fit: BoxFit.cover,  // How to resize
)

// From assets (local)
Image.asset('assets/images/logo.png')

// From file
Image.file(File('/path/to/image.jpg'))
```

**CircleAvatar:**

```dart
CircleAvatar(
  radius: 30,
  backgroundImage: NetworkImage('https://example.com/photo.jpg'),
  child: Text('A'),  // Fallback if no image
)
```

#### 12.3 Input widgets

**TextField:**

```dart
TextField(
  controller: _controller,   // Optional — for programmatic control
  decoration: InputDecoration(
    hintText: 'Enter your name',
    labelText: 'Name',
    prefixIcon: Icon(Icons.person),
    border: OutlineInputBorder(),
    filled: true,
    fillColor: Colors.grey[100],
  ),
  obscureText: true,          // For passwords
  keyboardType: TextInputType.emailAddress,
  textInputAction: TextInputAction.next,
  onChanged: (value) { /* called on each keystroke */ },
  onSubmitted: (value) { /* called when user presses enter */ },
  validator: (value) { /* for form validation */ },
)
```

**Checkbox and Switch:**

```dart
Checkbox(
  value: isChecked,
  onChanged: (v) => setState(() => isChecked = v!),
)

Switch(
  value: isEnabled,
  onChanged: (v) => setState(() => isEnabled = v),
)

CheckboxListTile(
  title: Text('Remember me'),
  subtitle: Text('Stay logged in'),
  value: isChecked,
  onChanged: (v) => setState(() => isChecked = v!),
)
```

**DropdownButton:**

```dart
String selectedCity = 'Karachi';

DropdownButton<String>(
  value: selectedCity,
  items: ['Karachi', 'Lahore', 'Islamabad'].map((city) =>
    DropdownMenuItem(value: city, child: Text(city))
  ).toList(),
  onChanged: (v) => setState(() => selectedCity = v!),
)
```

**DatePicker:**

```dart
Future<void> _pickDate() async {
  DateTime? picked = await showDatePicker(
    context: context,
    initialDate: DateTime.now(),
    firstDate: DateTime(2020),
    lastDate: DateTime(2030),
  );
  if (picked != null) {
    setState(() => _selectedDate = picked);
  }
}
```

#### 12.4 Interactive widgets

**ElevatedButton:**

```dart
ElevatedButton(
  onPressed: () { /* action */ },
  style: ElevatedButton.styleFrom(
    backgroundColor: Colors.blue,
    foregroundColor: Colors.white,
    padding: EdgeInsets.symmetric(horizontal: 24, vertical: 12),
    shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(8)),
  ),
  child: Text('Submit'),
)
```

**TextButton:**

```dart
TextButton(
  onPressed: () {},
  child: Text('Cancel'),
)
```

**OutlinedButton:**

```dart
OutlinedButton(
  onPressed: () {},
  child: Text('Learn More'),
)
```

**IconButton:**

```dart
IconButton(
  icon: Icon(Icons.favorite),
  color: Colors.red,
  onPressed: () {},
  tooltip: 'Add to favorites',
)
```

#### 12.5 List widgets

**ListView (simple):**

```dart
ListView(
  children: [
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
  ],
)
```

**ListView.builder (efficient for long lists):**

```dart
ListView.builder(
  itemCount: items.length,
  itemBuilder: (context, index) {
    return ListTile(
      leading: Icon(Icons.person),
      title: Text(items[index].name),
      subtitle: Text(items[index].description),
      trailing: Icon(Icons.arrow_forward),
      onTap: () { /* navigate to detail */ },
    );
  },
)
```

**GridView:**

```dart
GridView.builder(
  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 2,     // 2 columns
    crossAxisSpacing: 8,
    mainAxisSpacing: 8,
  ),
  itemCount: items.length,
  itemBuilder: (context, index) {
    return Card(child: Center(child: Text(items[index])));
  },
)
```

**ListTile:**

```dart
ListTile(
  leading: CircleAvatar(child: Text('A')),
  title: Text('Alice'),
  subtitle: Text('Online'),
  trailing: Icon(Icons.chat),
  onTap: () {},
  selected: true,
  enabled: true,
)
```

#### 12.6 Navigation widgets

**BottomNavigationBar:**

```dart
int _currentIndex = 0;

Scaffold(
  body: screens[_currentIndex],  // IndexedStack to keep alive
  bottomNavigationBar: BottomNavigationBar(
    currentIndex: _currentIndex,
    onTap: (i) => setState(() => _currentIndex = i),
    items: const [
      BottomNavigationBarItem(icon: Icon(Icons.home), label: 'Home'),
      BottomNavigationBarItem(icon: Icon(Icons.search), label: 'Search'),
      BottomNavigationBarItem(icon: Icon(Icons.person), label: 'Profile'),
    ],
  ),
)
```

**TabBar:**

```dart
DefaultTabController(
  length: 3,
  child: Scaffold(
    appBar: AppBar(
      title: Text('My App'),
      bottom: TabBar(
        tabs: [
          Tab(text: 'Tab 1'),
          Tab(text: 'Tab 2'),
          Tab(text: 'Tab 3'),
        ],
      ),
    ),
    body: TabBarView(
      children: [
        Text('Content 1'),
        Text('Content 2'),
        Text('Content 3'),
      ],
    ),
  ),
)
```

#### 12.7 Dialog widgets

**AlertDialog:**

```dart
showDialog(
  context: context,
  builder: (ctx) => AlertDialog(
    title: Text('Confirm'),
    content: Text('Are you sure?'),
    actions: [
      TextButton(
        onPressed: () => Navigator.pop(ctx),
        child: Text('Cancel'),
      ),
      TextButton(
        onPressed: () {
          // Confirm action
          Navigator.pop(ctx);
        },
        child: Text('OK'),
      ),
    ],
  ),
)
```

**BottomSheet:**

```dart
showModalBottomSheet(
  context: context,
  builder: (ctx) => Container(
    padding: EdgeInsets.all(16),
    child: Column(
      mainAxisSize: MainAxisSize.min,
      children: [
        Text('Options'),
        ListTile(title: Text('Option 1'), onTap: () {}),
        ListTile(title: Text('Option 2'), onTap: () {}),
      ],
    ),
  ),
)
```

**SnackBar:**

```dart
ScaffoldMessenger.of(context).showSnackBar(
  SnackBar(
    content: Text('Item deleted'),
    action: SnackBarAction(label: 'Undo', onPressed: () {}),
  ),
)
```

---

### Chapter 15: Project Setup — Creating Your First Flutter App

#### 13.1 Installing Flutter

Before writing any code, you need Flutter installed.

**System requirements:**
- Windows: 8 GB RAM, Windows 10+, Git
- macOS: 8 GB RAM, Xcode (for iOS)
- Linux: 8 GB RAM, Git

**Installation steps:**
```bash
# 1. Download Flutter SDK from flutter.dev
# 2. Extract to a folder (e.g., C:\flutter)
# 3. Add flutter\bin to your PATH
# 4. Verify installation
flutter doctor
```

`flutter doctor` checks everything is set up:
- Flutter SDK version
- Android toolchain (for Android builds)
- Xcode (for iOS/macOS builds)
- Chrome (for web)
- Connected devices

**If you see red X marks,** don't panic. Read the error message and follow the suggested fix.

#### 13.2 Creating a new project

```bash
flutter create my_app
cd my_app
```

This creates a complete project structure:

```
my_app/
├── android/         # Android-specific files (don't touch)
├── ios/             # iOS-specific files (don't touch)
├── web/             # Web-specific files (don't touch)
├── lib/             # YOUR CODE GOES HERE
│   └── main.dart    # Entry point of your app
├── test/            # Tests go here
├── pubspec.yaml     # Dependencies and project config
└── analysis_options.yaml  # Code quality rules
```

**99% of your work happens in `lib/`.** The other folders are platform-specific and rarely need changes.

#### 13.3 `pubspec.yaml` — Your project's control panel

```yaml
name: my_app
description: A new Flutter project.
publish_to: 'none'
version: 1.0.0+1

environment:
  sdk: '>=3.0.0 <4.0.0'

dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.6
  flutter_riverpod: ^3.3.2    # <-- Add packages here
  http: ^1.2.0                # <-- Another example

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^3.0.1
```

**Key sections:**
| Section | Purpose |
|---------|---------|
| `name` | Your app's package name (lowercase, underscores) |
| `version` | App version (major.minor.patch+build) |
| `environment` | Required Dart SDK version |
| `dependencies` | Packages your app needs at runtime |
| `dev_dependencies` | Packages only needed during development (testing, linting) |

**Adding a package:**
```yaml
# 1. Add the package name and version under dependencies
dependencies:
  http: ^1.2.0   # ^ means ">=1.2.0 <2.0.0"

# 2. Run this command in terminal
# flutter pub get
```

#### 13.4 Running the app

```bash
# List connected devices
flutter devices

# Run on connected device/emulator
flutter run

# Run with specific device
flutter run -d chrome        # Web
flutter run -d emulator-5554  # Android emulator
flutter run -d "iPhone 15"    # iOS simulator

# Hot reload (while app is running, press 'r' in terminal)
# Hot restart (press 'R')
```

**Hot reload** — injects code changes in <1 second without restarting the app. This is Flutter's superpower.

#### 13.5 Default folder structure in `lib/`

For a small project, keep it flat:

```
lib/
├── main.dart            # Entry point, ProviderScope, MaterialApp
├── models/              # Data classes (Todo, User, Product)
│   └── todo_model.dart
├── providers/           # Riverpod providers and notifiers
│   └── todo_provider.dart
├── screens/             # Full-page widgets
│   └── todo_screen.dart
└── widgets/             # Reusable small widgets
    └── todo_card.dart
```

**Import convention:**
```dart
// Absolute imports (preferred for lib/ files)
import 'package:my_app/models/todo_model.dart';

// Relative imports (acceptable for same-folder files)
import 'todo_model.dart';
```

#### 13.6 `main.dart` — The starting point

```dart
import 'package:flutter/material.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import 'screens/home_screen.dart';

void main() {
  runApp(
    const ProviderScope(
      child: MyApp(),
    ),
  );
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        useMaterial3: true,
      ),
      home: const HomeScreen(),
      debugShowCheckedModeBanner: false,
    );
  }
}
```

#### 13.7 Exercise: Create and run your first app

```bash
flutter create hello_flutter
cd hello_flutter
flutter run
```

Then modify `lib/main.dart` to show your name instead of the default counter app.

---

### Chapter 16: Navigation & Routing — Moving Between Screens

#### 16.1 What is navigation?

Navigation is moving from one screen to another. Every app has multiple screens:
- Home screen → Detail screen
- Product list → Product details
- Login → Dashboard

**Analogy:** A website has pages linked together. Flutter has screens pushed onto a stack.

```
Navigation stack (a stack of screens):
                    ┌─────────────┐
                    │ DetailScreen│  ← Top of stack (visible)
                    ├─────────────┤
                    │ HomeScreen  │
                    └─────────────┘
When you "push" → new screen goes on top (visible)
When you "pop"  → top screen is removed (previous screen visible)
```

#### 16.2 Basic navigation: `Navigator.push` and `Navigator.pop`

```dart
// Screen 1 — Home
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Home')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // Navigate to DetailScreen
            Navigator.push(
              context,
              MaterialPageRoute(
                builder: (ctx) => const DetailScreen(itemId: 42),
              ),
            );
          },
          child: Text('Open Details'),
        ),
      ),
    );
  }
}

// Screen 2 — Detail
class DetailScreen extends StatelessWidget {
  final int itemId;
  const DetailScreen({required this.itemId, super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Item $itemId')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // Go back to previous screen
            Navigator.pop(context);
          },
          child: Text('Go Back'),
        ),
      ),
    );
  }
}
```

#### 16.3 Passing data between screens

**Forward (Screen A → Screen B):**
```dart
// Pass via constructor — simple and type-safe
class DetailScreen extends StatelessWidget {
  final int userId;
  final String userName;
  const DetailScreen({
    required this.userId,
    required this.userName,
    super.key,
  });
  // ...
}

// Navigate:
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (ctx) => DetailScreen(userId: 1, userName: 'Alice'),
  ),
);
```

**Backward (Screen B → Screen A):**
```dart
// Screen B returns a result when popping
Navigator.pop(context, 'Deleted');  // Pass result back

// Screen A awaits the result
final result = await Navigator.push<String>(
  context,
  MaterialPageRoute(builder: (ctx) => const EditScreen()),
);
// result = 'Deleted' (or null if user pressed back without pop)
```

#### 16.4 Named routes (simple but limited)

```dart
// In MaterialApp:
MaterialApp(
  initialRoute: '/',
  routes: {
    '/': (ctx) => const HomeScreen(),
    '/settings': (ctx) => const SettingsScreen(),
    '/about': (ctx) => const AboutScreen(),
  },
)

// Navigate:
Navigator.pushNamed(context, '/settings');
Navigator.pushNamed(context, '/about');

// Go back:
Navigator.pop(context);
```

**Limitation:** Can't pass parameters easily. For parameters, use `onGenerateRoute` or GoRouter.

#### 16.5 GoRouter — The professional way

GoRouter is the recommended routing package for Flutter. Add it:

```yaml
dependencies:
  go_router: ^14.0.0
```

**Basic setup:**
```dart
import 'package:flutter/material.dart';
import 'package:go_router/go_router.dart';

// Define routes
final router = GoRouter(
  initialLocation: '/',
  routes: [
    GoRoute(
      path: '/',
      name: 'home',
      builder: (context, state) => const HomeScreen(),
    ),
    GoRoute(
      path: '/settings',
      name: 'settings',
      builder: (context, state) => const SettingsScreen(),
    ),
    GoRoute(
      path: '/profile/:userId',  // :userId = path parameter
      name: 'profile',
      builder: (context, state) {
        final userId = state.pathParameters['userId']!;
        return ProfileScreen(userId: userId);
      },
    ),
  ],
);

// Use in MaterialApp:
MaterialApp.router(
  routerConfig: router,  // ← Use .router constructor
  title: 'My App',
);

// Navigate:
context.go('/');                    // Go to home
context.go('/settings');            // Go to settings
context.go('/profile/42');          // Go to profile, userId=42
context.push('/settings');          // Push onto stack (can pop back)
context.pop();                      // Go back
```

**Key GoRouter features:**
| Feature | How |
|---------|-----|
| Path parameters | `/user/:id` → `state.pathParameters['id']` |
| Query parameters | `/search?q=hello` → `state.uri.queryParameters['q']` |
| Named routes | `context.goNamed('profile', pathParameters: {'userId': '42'})` |
| Deep linking | URLs work on web, push notifications, etc. |
| Nesting | Routes inside routes (for BottomNavigationBar) |

#### 16.6 Nested navigation with GoRouter (tab bar)

```dart
final router = GoRouter(
  initialLocation: '/home',
  routes: [
    // ShellRoute creates a wrapper widget (keeps BottomNav alive)
    ShellRoute(
      builder: (context, state, child) => MainShell(child: child),
      routes: [
        GoRoute(
          path: '/home',
          pageBuilder: (context, state) => NoTransitionPage(
            child: HomeScreen(),
          ),
        ),
        GoRoute(
          path: '/search',
          pageBuilder: (context, state) => NoTransitionPage(
            child: SearchScreen(),
          ),
        ),
        GoRoute(
          path: '/profile',
          pageBuilder: (context, state) => NoTransitionPage(
            child: ProfileScreen(),
          ),
        ),
      ],
    ),
  ],
);

// Main shell widget
class MainShell extends StatelessWidget {
  final Widget child;
  const MainShell({required this.child, super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: child,
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: _calculateIndex(context),
        onTap: (i) => _goToTab(context, i),
        items: const [
          BottomNavigationBarItem(icon: Icon(Icons.home), label: 'Home'),
          BottomNavigationBarItem(icon: Icon(Icons.search), label: 'Search'),
          BottomNavigationBarItem(icon: Icon(Icons.person), label: 'Profile'),
        ],
      ),
    );
  }

  int _calculateIndex(BuildContext context) {
    final location = GoRouterState.of(context).uri.toString();
    if (location.startsWith('/home')) return 0;
    if (location.startsWith('/search')) return 1;
    if (location.startsWith('/profile')) return 2;
    return 0;
  }

  void _goToTab(BuildContext context, int index) {
    switch (index) {
      case 0: context.go('/home');
      case 1: context.go('/search');
      case 2: context.go('/profile');
    }
  }
}
```

#### 16.7 Navigation with Riverpod

```dart
// Navigation notifier — for complex navigation logic
class NavigationNotifier extends Notifier<String> {
  @override
  String build() => '/home';

  void goToHome() => state = '/home';
  void goToProfile(String id) => state = '/profile/$id';
  void goBack() {
    // In a real app, you'd use GoRouter's context.go()
    // This pattern is for special cases like redirect after login
  }
}

final navigationProvider = NotifierProvider<NavigationNotifier, String>(
  () => NavigationNotifier(),
);
```

**Best practice:** Keep navigation in the widget layer (GoRouter handles it). Use Riverpod for navigation state only in complex cases (auth redirect, onboarding flow).

#### 16.8 Common navigation mistakes

```dart
// ❌ Using context after async gap (widget might be disposed)
void _navigate() async {
  await someFuture();
  if (!context.mounted) return;  // ← Critical check!
  Navigator.push(context, ...);
}

// ✅ Same, but with mounted check
void _navigate() async {
  await someFuture();
  if (!context.mounted) return;  // Prevents crash
  Navigator.push(context, ...);
}

// ❌ Forgetting context.mounted in async code
// If user navigated away while future was loading, context is stale
```

#### 16.9 Exercise: Build a two-screen app

Create a home screen with a list of names. Tapping a name navigates to a detail screen showing that name. Use GoRouter.

```dart
// Solution outline:
class HomeScreen extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final names = ['Alice', 'Bob', 'Charlie'];
    return Scaffold(
      appBar: AppBar(title: Text('Contacts')),
      body: ListView.builder(
        itemCount: names.length,
        itemBuilder: (ctx, i) => ListTile(
          title: Text(names[i]),
          onTap: () => context.go('/profile/${names[i]}'),
        ),
      ),
    );
  }
}

// GoRouter:
GoRoute(
  path: '/profile/:name',
  builder: (ctx, state) => ProfileScreen(
    name: state.pathParameters['name']!,
  ),
)
```

---

### Chapter 15: HTTP & API Integration — Talking to the Internet

#### 15.1 How apps talk to servers

```
Your App                     Server (API)
    │                            │
    │─── GET /api/users ────────→│  ← Request
    │                            │
    │←───── JSON data ──────────│  ← Response
    │     [{id:1,name:"Alice"}]  │
```

**Key terms:**
| Term | Meaning |
|------|---------|
| **API** | Application Programming Interface — how apps talk to servers |
| **HTTP** | The protocol used for communication |
| **GET** | Fetch data (read) |
| **POST** | Send data (create) |
| **PUT/PATCH** | Update data |
| **DELETE** | Remove data |
| **JSON** | Data format (like a Map with strings, numbers, lists) |
| **Endpoint** | A specific URL that returns data (e.g., `https://api.example.com/users`) |
| **Status code** | Response status: 200=OK, 201=Created, 400=Bad Request, 404=Not Found, 500=Server Error |

#### 15.2 Setting up the `http` package

```yaml
dependencies:
  http: ^1.2.0
```

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';  // For jsonEncode/jsonDecode
```

#### 15.3 Making a GET request

```dart
Future<List<Map<String, dynamic>>> fetchUsers() async {
  // 1. Make the request
  final response = await http.get(
    Uri.parse('https://jsonplaceholder.typicode.com/users'),
    headers: {'Content-Type': 'application/json'},
  );

  // 2. Check status code
  if (response.statusCode == 200) {
    // 3. Parse JSON response
    final List<dynamic> data = jsonDecode(response.body);
    return data.cast<Map<String, dynamic>>();
  } else {
    throw Exception('Failed to load users: ${response.statusCode}');
  }
}
```

**Line by line:**
| Code | Purpose |
|------|---------|
| `http.get(Uri.parse(...))` | Send GET request to URL |
| `headers:` | Extra info (auth tokens, content type) |
| `response.statusCode` | 200 = success, others = failure |
| `jsonDecode(response.body)` | Convert JSON string to Dart objects |
| `throw Exception(...)` | Signal that something went wrong |

#### 15.4 Making POST, PUT, DELETE requests

```dart
// POST — create new data
Future<Map<String, dynamic>> createUser(String name, String email) async {
  final response = await http.post(
    Uri.parse('https://jsonplaceholder.typicode.com/users'),
    headers: {'Content-Type': 'application/json'},
    body: jsonEncode({
      'name': name,
      'email': email,
    }),
  );

  if (response.statusCode == 201) {  // 201 = Created
    return jsonDecode(response.body);
  }
  throw Exception('Failed to create user');
}

// PUT — update existing data
Future<void> updateUser(int id, String name) async {
  final response = await http.put(
    Uri.parse('https://jsonplaceholder.typicode.com/users/$id'),
    headers: {'Content-Type': 'application/json'},
    body: jsonEncode({'name': name}),
  );

  if (response.statusCode != 200) {
    throw Exception('Failed to update user');
  }
}

// DELETE — remove data
Future<void> deleteUser(int id) async {
  final response = await http.delete(
    Uri.parse('https://jsonplaceholder.typicode.com/users/$id'),
  );

  if (response.statusCode != 200) {
    throw Exception('Failed to delete user');
  }
}
```

#### 15.5 JSON to Model conversion

Always convert raw JSON into typed Dart objects:

```dart
// Model class
class User {
  final int id;
  final String name;
  final String email;
  final String phone;

  const User({
    required this.id,
    required this.name,
    required this.email,
    required this.phone,
  });

  // Factory constructor: creates User from JSON map
  factory User.fromJson(Map<String, dynamic> json) {
    return User(
      id: json['id'] as int,
      name: json['name'] as String,
      email: json['email'] as String,
      phone: json['phone'] as String,
    );
  }

  // Converts User back to JSON map
  Map<String, dynamic> toJson() => {
    'id': id,
    'name': name,
    'email': email,
    'phone': phone,
  };
}

// Using it:
final response = await http.get(Uri.parse('...'));
final List<dynamic> jsonList = jsonDecode(response.body);
final List<User> users = jsonList.map((j) => User.fromJson(j)).toList();
```

**Why `fromJson` / `toJson`?**
- `fromJson`: convert JSON → Dart object (when receiving from server)
- `toJson`: convert Dart object → JSON (when sending to server)
- Keeps JSON parsing in one place (not scattered across your code)

#### 15.6 API service class

Organize all API calls in a single class:

```dart
class ApiService {
  final String baseUrl = 'https://jsonplaceholder.typicode.com';
  final http.Client _client = http.Client();

  Future<List<User>> getUsers() async {
    final response = await _client.get(Uri.parse('$baseUrl/users'));
    if (response.statusCode == 200) {
      final List<dynamic> data = jsonDecode(response.body);
      return data.map((j) => User.fromJson(j)).toList();
    }
    throw ApiException('Failed to load users', response.statusCode);
  }

  Future<User> getUser(int id) async {
    final response = await _client.get(Uri.parse('$baseUrl/users/$id'));
    if (response.statusCode == 200) {
      return User.fromJson(jsonDecode(response.body));
    }
    throw ApiException('Failed to load user', response.statusCode);
  }

  Future<User> createUser(String name, String email) async {
    final response = await _client.post(
      Uri.parse('$baseUrl/users'),
      body: jsonEncode({'name': name, 'email': email}),
    );
    if (response.statusCode == 201) {
      return User.fromJson(jsonDecode(response.body));
    }
    throw ApiException('Failed to create user', response.statusCode);
  }

  void dispose() => _client.close();
}

class ApiException implements Exception {
  final String message;
  final int statusCode;
  const ApiException(this.message, this.statusCode);

  @override
  String toString() => 'ApiException($statusCode): $message';
}
```

#### 15.7 API calls with Riverpod

```dart
// State — loading, data, error
class UserListState {
  final bool loading;
  final List<User> users;
  final String? error;

  const UserListState({
    this.loading = false,
    this.users = const [],
    this.error,
  });

  UserListState copyWith({bool? loading, List<User>? users, String? error}) =>
    UserListState(
      loading: loading ?? this.loading,
      users: users ?? this.users,
      error: error ?? this.error,
    );
}

// Notifier — manages API calls
class UserListNotifier extends Notifier<UserListState> {
  final ApiService _api = ApiService();

  @override
  UserListState build() => const UserListState();

  Future<void> loadUsers() async {
    state = state.copyWith(loading: true, error: null);
    try {
      final users = await _api.getUsers();
      state = state.copyWith(loading: false, users: users);
    } catch (e) {
      state = state.copyWith(loading: false, error: e.toString());
    }
  }

  @override
  void dispose() {
    _api.dispose();
    super.dispose();
  }
}

final userListProvider = NotifierProvider<UserListNotifier, UserListState>(
  () => UserListNotifier(),
);
```

#### 15.8 Screen with API data

```dart
class UserListScreen extends ConsumerWidget {
  const UserListScreen({super.key});

  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final state = ref.watch(userListProvider);

    // Trigger initial load once
    ref.listenManual(userListProvider, (prev, next) {
      if (prev == null) ref.read(userListProvider.notifier).loadUsers();
    });

    return Scaffold(
      appBar: AppBar(title: Text('Users')),
      body: _buildBody(state, ref),
    );
  }

  Widget _buildBody(UserListState state, WidgetRef ref) {
    if (state.loading) {
      return const Center(child: CircularProgressIndicator());
    }

    if (state.error != null) {
      return Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(Icons.error_outline, size: 48, color: Colors.red),
            SizedBox(height: 16),
            Text('Error: ${state.error}'),
            SizedBox(height: 16),
            ElevatedButton(
              onPressed: () => ref.read(userListProvider.notifier).loadUsers(),
              child: Text('Retry'),
            ),
          ],
        ),
      );
    }

    return RefreshIndicator(
      onRefresh: () => ref.read(userListProvider.notifier).loadUsers(),
      child: ListView.builder(
        itemCount: state.users.length,
        itemBuilder: (ctx, i) {
          final user = state.users[i];
          return ListTile(
            leading: CircleAvatar(child: Text('${user.id}')),
            title: Text(user.name),
            subtitle: Text(user.email),
          );
        },
      ),
    );
  }
}
```

#### 15.9 Common HTTP mistakes

```dart
// ❌ Forgetting to import dart:convert
final data = jsonDecode(response.body);  // Error: undefined

// ✅ Import it
import 'dart:convert';

// ❌ Not handling errors
final response = await http.get(...);
// If network fails, this throws an unhandled exception

// ✅ Always wrap in try/catch
try {
  final response = await http.get(...);
} catch (e) {
  // Handle error
}

// ❌ Not checking status code
final data = jsonDecode(response.body);  // Crash if 404 with HTML body

// ✅ Always check
if (response.statusCode == 200) { ... }

// ❌ Hardcoding URLs everywhere
final x = await http.get(Uri.parse('https://api.example.com/v2/users/42'));

// ✅ Use constants
class Endpoints {
  static const baseUrl = 'https://api.example.com/v2';
  static String user(int id) => '$baseUrl/users/$id';
}
```

#### 15.10 Exercise: Fetch and display a list

1. Create a `Post` model with `id`, `title`, `body` fields
2. Create an `ApiService` that fetches posts from `https://jsonplaceholder.typicode.com/posts`
3. Create a Riverpod notifier to manage loading state
4. Display posts in a `ListView`

```dart
// Post model
class Post {
  final int id;
  final String title;
  final String body;

  const Post({required this.id, required this.title, required this.body});

  factory Post.fromJson(Map<String, dynamic> json) => Post(
    id: json['id'] as int,
    title: json['title'] as String,
    body: json['body'] as String,
  );
}
```

---

### Chapter 16: Responsive & Adaptive Design — Working on Any Screen

#### 16.1 What is responsive design?

A **responsive** app looks good on any screen size:

```
Phone (360×800)        Tablet (600×1024)       Desktop (1920×1080)
┌──────────┐           ┌──────────────┐        ┌──────────────────────┐
│ ┌──────┐ │           │ ┌───┐ ┌───┐  │        │ ┌──┐ ┌──┐ ┌──┐ ┌──┐ │
│ │Card 1│ │           │ │ 1 │ │ 2 │  │        │ │1 │ │2 │ │3 │ │4 │ │
│ └──────┘ │           │ └───┘ └───┘  │        │ └──┘ └──┘ └──┘ └──┘ │
│ ┌──────┐ │           │ ┌───┐ ┌───┐  │        │ ┌──┐ ┌──┐ ┌──┐ ┌──┐ │
│ │Card 2│ │           │ │ 3 │ │ 4 │  │        │ │5 │ │6 │ │7 │ │8 │ │
│ └──────┘ │           │ └───┘ └───┘  │        │ └──┘ └──┘ └──┘ └──┘ │
└──────────┘           └──────────────┘        └──────────────────────┘
  1 column                2 columns                 4 columns
```

#### 16.2 `MediaQuery` — Screen information

```dart
// Get screen dimensions
final size = MediaQuery.of(context).size;
final width = size.width;
final height = size.height;

// Get orientation
final orientation = MediaQuery.of(context).orientation;

// Get padding (notch, status bar, bottom bar)
final padding = MediaQuery.of(context).padding;

// Check keyboard visibility
final isKeyboardVisible = MediaQuery.of(context).viewInsets.bottom > 0;

// Example: responsive padding
final horizontalPadding = width > 600 ? 32.0 : 16.0;
```

#### 16.3 `LayoutBuilder` — Build based on available space

```dart
LayoutBuilder(
  builder: (context, constraints) {
    // constraints has: maxWidth, maxHeight, minWidth, minHeight

    if (constraints.maxWidth > 600) {
      // Wide layout (tablet/desktop)
      return Row(
        children: [
          Expanded(flex: 1, child: Sidebar()),
          Expanded(flex: 3, child: MainContent()),
        ],
      );
    } else {
      // Narrow layout (phone)
      return Column(
        children: [
          TopBar(),
          Expanded(child: MainContent()),
        ],
      );
    }
  },
)
```

#### 16.4 Breakpoints — Screen size categories

```dart
class Breakpoints {
  static const double phone = 600;
  static const double tablet = 900;
  static const double desktop = 1200;

  static bool isPhone(BuildContext context) =>
    MediaQuery.of(context).size.width < phone;

  static bool isTablet(BuildContext context) {
    final w = MediaQuery.of(context).size.width;
    return w >= phone && w < desktop;
  }

  static bool isDesktop(BuildContext context) =>
    MediaQuery.of(context).size.width >= desktop;
}

// Usage:
if (Breakpoints.isPhone(context)) {
  // Mobile layout
} else if (Breakpoints.isTablet(context)) {
  // Tablet layout
} else {
  // Desktop layout
}
```

#### 16.5 `Flexible` and `Expanded` — Proportional sizing

```dart
// Expanded — takes ALL remaining space
Row(
  children: [
    Text('Left'),
    Expanded(child: Text('This gets all remaining space')),
    Text('Right'),
  ],
)

// Flexible — takes remaining space BUT can shrink if needed
Row(
  children: [
    Flexible(flex: 2, child: SidePanel()),
    Flexible(flex: 3, child: MainContent()),
    // SidePanel gets 2/5, MainContent gets 3/5 of available space
  ],
)

// AspectRatio — maintain proportions
AspectRatio(
  aspectRatio: 16 / 9,  // Width:Height ratio
  child: Container(color: Colors.blue),
)
```

#### 16.6 Adaptive widgets — Platform-specific look

```dart
// Switch between Material (Android) and Cupertino (iOS)
import 'dart:io' show Platform;

Widget buildSwitch({required bool value, required ValueChanged<bool> onChanged}) {
  if (Platform.isIOS) {
    return CupertinoSwitch(value: value, onChanged: onChanged);
  }
  return Switch(value: value, onChanged: onChanged);
}

// Or use Theme判断:
import 'package:flutter/cupertino.dart';

Widget buildAdaptiveButton({required String text, required VoidCallback onPressed}) {
  if (Theme.of(context).platform == TargetPlatform.iOS) {
    return CupertinoButton.filled(child: Text(text), onPressed: onPressed);
  }
  return ElevatedButton(onPressed: onPressed, child: Text(text));
}
```

#### 16.7 Orientation changes

```dart
// Lock orientation (in main.dart)
void main() {
  WidgetsFlutterBinding.ensureInitialized();
  SystemChrome.setPreferredOrientations([
    DeviceOrientation.portraitUp,
    // DeviceOrientation.landscapeLeft,  // Optionally allow landscape
  ]);
  runApp(const MyApp());
}

// React to orientation
@override
Widget build(BuildContext context) {
  final isLandscape = MediaQuery.of(context).orientation == Orientation.landscape;

  return isLandscape
      ? LandscapeLayout()
      : PortraitLayout();
}
```

#### 16.8 SafeArea — Avoid notches and status bars

```dart
// SafeArea adds padding to avoid screen cutouts
Scaffold(
  body: SafeArea(
    top: true,      // Avoid status bar
    bottom: true,   // Avoid home indicator
    child: Column(
      children: [
        Text('This won't go under the status bar'),
      ],
    ),
  ),
)
```

#### 16.9 Exercise: Build a responsive dashboard

Create a screen that shows cards in:
- 1 column on phones (<600px)
- 2 columns on tablets (600-900px)
- 3 columns on desktop (>900px)

```dart
class ResponsiveDashboard extends StatelessWidget {
  const ResponsiveDashboard({super.key});

  @override
  Widget build(BuildContext context) {
    return LayoutBuilder(
      builder: (context, constraints) {
        int crossAxisCount;
        if (constraints.maxWidth > 900) {
          crossAxisCount = 3;
        } else if (constraints.maxWidth > 600) {
          crossAxisCount = 2;
        } else {
          crossAxisCount = 1;
        }

        return GridView.builder(
          padding: EdgeInsets.all(16),
          gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
            crossAxisCount: crossAxisCount,
            crossAxisSpacing: 16,
            mainAxisSpacing: 16,
            childAspectRatio: 1.5,
          ),
          itemCount: 6,
          itemBuilder: (ctx, i) => Card(
            child: Center(child: Text('Card ${i + 1}')),
          ),
        );
      },
    );
  }
}
```

---

### Chapter 17: Animations — Making Your App Come Alive

#### 17.1 Why animations?

Animations make apps feel polished:
- **Feedback**: Button press → visual response
- **Context**: New item slides in, old item slides out
- **Flow**: Smooth transitions between screens
- **Delight**: A well-timed animation makes users smile

**Rule of thumb:** Animations should be subtle. 200-300ms is usually the right duration.

#### 17.2 `AnimatedContainer` — Easiest animation

```dart
class ExpandableCard extends StatefulWidget {
  @override
  State<ExpandableCard> createState() => _ExpandableCardState();
}

class _ExpandableCardState extends State<ExpandableCard> {
  bool _expanded = false;

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => setState(() => _expanded = !_expanded),
      child: AnimatedContainer(
        duration: Duration(milliseconds: 300),  // Animation duration
        curve: Curves.easeInOut,                  // Acceleration curve
        width: _expanded ? 300 : 150,
        height: _expanded ? 200 : 100,
        decoration: BoxDecoration(
          color: _expanded ? Colors.blue : Colors.grey,
          borderRadius: BorderRadius.circular(16),
        ),
        child: Center(
          child: Text(
            _expanded ? 'Tap to shrink' : 'Tap to expand',
            style: TextStyle(color: Colors.white),
          ),
        ),
      ),
    );
  }
}
```

**What changes?** `AnimatedContainer` automatically animates any property that changes between builds: width, height, color, padding, margin, border radius, etc.

#### 17.3 `AnimatedOpacity` — Fade in/out

```dart
class FadeWidget extends StatefulWidget {
  @override
  State<FadeWidget> createState() => _FadeWidgetState();
}

class _FadeWidgetState extends State<FadeWidget> {
  bool _visible = true;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        AnimatedOpacity(
          duration: Duration(milliseconds: 500),
          opacity: _visible ? 1.0 : 0.0,
          child: Container(
            width: 200, height: 200,
            color: Colors.blue,
            child: Center(child: Text('Hello')),
          ),
        ),
        ElevatedButton(
          onPressed: () => setState(() => _visible = !_visible),
          child: Text('Toggle'),
        ),
      ],
    );
  }
}
```

#### 17.4 `TweenAnimationBuilder` — Custom animations

```dart
class ProgressCircle extends StatelessWidget {
  final double progress;  // 0.0 to 1.0

  const ProgressCircle({required this.progress});

  @override
  Widget build(BuildContext context) {
    return TweenAnimationBuilder<double>(
      tween: Tween(begin: 0, end: progress),
      duration: Duration(seconds: 1),
      curve: Curves.easeOutCubic,
      builder: (context, value, child) {
        return SizedBox(
          width: 100, height: 100,
          child: CircularProgressIndicator(
            value: value,
            strokeWidth: 8,
            backgroundColor: Colors.grey[200],
            valueColor: AlwaysStoppedAnimation(Colors.blue),
          ),
        );
      },
    );
  }
}
```

**Common tweens:**

| Tween | Purpose |
|-------|---------|
| `Tween<double>(begin: 0, end: 1)` | Numbers |
| `ColorTween(begin: Colors.red, end: Colors.blue)` | Colors |
| `SizeTween(begin: Size(0,0), end: Size(100,100))` | Sizes |
| `AlignmentTween(begin: Alignment.topLeft, end: Alignment.bottomRight)` | Positions |

#### 17.5 `Hero` — Screen transition animation

```dart
// Screen A (list)
Hero(
  tag: 'item-${item.id}',  // Must match between screens!
  child: Image.network(item.imageUrl, width: 100, height: 100),
)

// Screen B (detail)
Hero(
  tag: 'item-${item.id}',  // Same tag!
  child: Image.network(item.imageUrl, width: 300, height: 300),
)

// Flutter automatically animates the image from Screen A position/size
// to Screen B position/size during navigation. Looks magical!
```

**How Hero works:**
1. Flutter finds widgets with matching `tag` on both screens
2. During navigation, it creates a "flying" copy of the widget
3. The copy animates from the source position to the destination position
4. When animation completes, the destination widget becomes visible

#### 17.6 `AnimatedList` — List with insert/remove animations

```dart
class AnimatedListExample extends StatefulWidget {
  @override
  State<AnimatedListExample> createState() => _AnimatedListExampleState();
}

class _AnimatedListExampleState extends State<AnimatedListExample> {
  final _listKey = GlobalKey<AnimatedListState>();
  final _items = <String>['Item 1', 'Item 2', 'Item 3'];

  void _addItem() {
    _items.insert(0, 'New Item');
    _listKey.currentState?.insertItem(0, duration: Duration(milliseconds: 300));
  }

  void _removeItem(int index) {
    final item = _items.removeAt(index);
    _listKey.currentState?.removeItem(
      index,
      (context, animation) => SizeTransition(
        sizeFactor: animation,
        child: Card(child: ListTile(title: Text(item))),
      ),
      duration: Duration(milliseconds: 300),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        ElevatedButton(onPressed: _addItem, child: Text('Add')),
        Expanded(
          child: AnimatedList(
            key: _listKey,
            initialItemCount: _items.length,
            itemBuilder: (ctx, index, animation) {
              return SizeTransition(
                sizeFactor: animation,
                child: Card(
                  child: ListTile(
                    title: Text(_items[index]),
                    trailing: IconButton(
                      icon: Icon(Icons.delete),
                      onPressed: () => _removeItem(index),
                    ),
                  ),
                ),
              );
            },
          ),
        ),
      ],
    );
  }
}
```

#### 17.7 `AnimatedSwitcher` — Smooth widget switching

```dart
class ScreenSwitcher extends StatefulWidget {
  @override
  State<ScreenSwitcher> createState() => _ScreenSwitcherState();
}

class _ScreenSwitcherState extends State<ScreenSwitcher> {
  bool _isFirst = true;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        AnimatedSwitcher(
          duration: Duration(milliseconds: 500),
          transitionBuilder: (child, animation) {
            return FadeTransition(opacity: animation, child: child);
          },
          child: _isFirst
            ? Container(key: ValueKey('first'), color: Colors.blue, height: 200)
            : Container(key: ValueKey('second'), color: Colors.red, height: 200),
          // Key is critical! Flutter uses it to detect "new" vs "old" widget
        ),
        ElevatedButton(
          onPressed: () => setState(() => _isFirst = !_isFirst),
          child: Text('Switch'),
        ),
      ],
    );
  }
}
```

**IMPORTANT:** Each child MUST have a unique `Key`. Without it, Flutter thinks nothing changed and won't animate.

#### 17.8 Animation curves

```dart
// Built-in curves — try different ones:
Curves.easeIn;             // Slow start, fast end
Curves.easeOut;            // Fast start, slow end
Curves.easeInOut;          // Slow start+end, fast middle
Curves.bounceIn;           // Bouncy at start
Curves.bounceOut;          // Bouncy at end
Curves.elasticOut;         // Overshoots then settles
Curves.fastOutSlowIn;      // Material Design standard

// Usage:
AnimatedContainer(
  duration: Duration(milliseconds: 300),
  curve: Curves.bounceOut,
  // ...
)
```

#### 17.9 Performance tips

```dart
// ❌ Animating layout properties (triggers expensive layout pass)
AnimatedContainer(
  width: newWidth,     // Triggers layout
  height: newHeight,   // Triggers layout
)

// ✅ Animating transform (uses GPU, much cheaper)
Transform.translate(
  offset: Offset(100, 0),  // Animate this instead of margin/position
  child: myWidget,
)

// ❌ Animating large images
// ✅ Use a smaller version of the image for animation, swap at end

// ❌ Animating during a heavy build
// ✅ Use RepaintBoundary to isolate animation from rest of widget tree
RepaintBoundary(
  child: AnimatedWidget(...),
)
```

#### 17.10 Exercise: Animated todo item

Create a todo item that:
- Fades in when added
- Slides out when deleted
- Changes color smoothly when toggled done

```dart
class AnimatedTodoItem extends StatelessWidget {
  final String title;
  final bool isDone;
  final VoidCallback onToggle;
  final VoidCallback onDelete;

  const AnimatedTodoItem({
    required this.title,
    required this.isDone,
    required this.onToggle,
    required this.onDelete,
  });

  @override
  Widget build(BuildContext context) {
    return AnimatedContainer(
      duration: Duration(milliseconds: 300),
      curve: Curves.easeInOut,
      decoration: BoxDecoration(
        color: isDone ? Colors.green[50] : Colors.white,
        borderRadius: BorderRadius.circular(8),
      ),
      child: ListTile(
        leading: Checkbox(value: isDone, onChanged: (_) => onToggle()),
        title: AnimatedDefaultTextStyle(
          duration: Duration(milliseconds: 300),
          style: TextStyle(
            decoration: isDone ? TextDecoration.lineThrough : null,
            color: isDone ? Colors.grey : Colors.black,
          ),
          child: Text(title),
        ),
        trailing: IconButton(
          icon: AnimatedSwitcher(
            duration: Duration(milliseconds: 200),
            child: isDone
              ? Icon(Icons.check_circle, color: Colors.green, key: ValueKey('done'))
              : Icon(Icons.delete_outline, color: Colors.red, key: ValueKey('delete')),
          ),
          onPressed: isDone ? onDelete : onToggle,
        ),
      ),
    );
  }
}
```

---

### Chapter 18: Debugging & Tools — Fixing Problems

#### 18.1 Understanding errors

When Flutter crashes, the **debug console** shows an error. Learn to read it:

```
════════ Exception caught by gesture ═══════════════════════════════════
The following _TypeError was thrown while handling a gesture:
Null check operator used on a null value   ← What happened

When the exception was thrown, this was the stack:  ← Where it happened
#0  main (file:///.../main.dart:12:5)
#1  ...

════════════════════════════════════════════════════════════════════════
```

**How to read a stack trace:**
1. **Look at the top** — the error message tells you WHAT
2. **Look at the first file reference** — tells you WHERE (`main.dart:12` = line 12)
3. **Ignore framework internals** — focus on YOUR files (lib/...)

#### 18.2 `print()` and `debugPrint()`

```dart
// Simple debugging
void someFunction() {
  print('someFunction called with x=$x');  // Prints to console
}

// Better: debugPrint — won't be truncated
import 'package:flutter/foundation.dart';

void someFunction() {
  debugPrint('someFunction called with x=$x');
}

// Log multiple values
debugPrint('State: loading=$loading, error=$error, data=$data');
```

**`debugPrint()` vs `print()`:**
- `print()` — can be truncated if too much output
- `debugPrint()` — guaranteed to print full output
- Both only show in debug mode (not in production)

#### 18.3 The Flutter Inspector

The Flutter Inspector is your best friend for UI debugging.

**How to open:**
- VS Code: View → Command Palette → "Flutter: Open Inspector"
- Android Studio: Flutter Inspector tab
- Command line: Press 'i' in `flutter run` terminal

**What you can do:**
| Feature | How |
|---------|-----|
| Select widget | Click on the device screen → Inspector highlights it |
| View properties | See padding, margin, size, color of any widget |
| See widget tree | Visual tree showing parent/child relationships |
| Toggle guidelines | Show layout boundaries, baselines, repaint regions |
| Debug paint | `debugPaintSizeEnabled = true` in code |

#### 18.4 Debug flags

```dart
import 'package:flutter/rendering.dart';

void main() {
  // Show layout boundaries (boxes around all widgets)
  debugPaintSizeEnabled = true;

  // Show repaint boundaries (green borders = repaint on change)
  debugRepaintRainbowEnabled = true;

  runApp(const MyApp());
}
```

#### 18.5 Common error types and solutions

| Error | Cause | Fix |
|-------|-------|-----|
| `Null check operator used on null` | Using `!` on null value | Add null check (`if (x != null)`) or use `?.` |
| `RenderBox was not laid out` | Widget has unbounded height in scroll | Wrap in `Expanded` or give explicit `height` |
| `setState called during build` | Calling `setState()` inside `build()` | Move to `initState()` or callback |
| `Aspect ratio is infinite` | `Expanded` inside `IntrinsicHeight` or similar | Use `Flexible` or fixed sizes |
| `Multiple widgets used the same GlobalKey` | Two widgets sharing a GlobalKey | Use ValueKey or UniqueKey instead |
| `setState() called after dispose()` | Async callback after widget removed | Check `mounted` before setState |

#### 18.6 Debugging Riverpod

```dart
// Log all state changes
final counterProvider = NotifierProvider<CounterNotifier, CounterState>(
  () => CounterNotifier(),
  name: 'counter',  // Give providers names for debugging
);

// In build method:
@override
Widget build(BuildContext context, WidgetRef ref) {
  // Log when widget rebuilds
  debugPrint('CounterScreen built');
  final count = ref.watch(counterProvider);
  debugPrint('CounterScreen: count=$count');
  // ...
}

// Provider lifecycle debugging
class MyNotifier extends Notifier<MyState> {
  @override
  MyState build() {
    debugPrint('MyNotifier created');   // Called once
    return const MyState();
  }

  @override
  void dispose() {
    debugPrint('MyNotifier disposed');  // Called when no more watchers
    super.dispose();
  }
}
```

#### 18.7 Slow app? Performance profiling

```dart
// 1. Check rebuild count — are widgets rebuilding too often?
// In Flutter Inspector: "Track Widget Rebuilds"

// 2. Use RepaintBoundary for expensive widgets
RepaintBoundary(
  child: ExpensiveMapWidget(),  // Only repaints this, not whole screen
)

// 3. Avoid creating new objects in build()
// ❌ Created every rebuild
@override
Widget build(context) {
  return Text('${DateTime.now()}');  // New string every frame
}

// ✅ Use const where possible
const Text('Fixed text');

// 4. ListView.builder for long lists (not ListView(children:[...]))
ListView.builder(  // Lazy — builds only visible items
  itemCount: 100000,
  itemBuilder: (ctx, i) => Text('Item $i'),
)
```

#### 18.8 The `mounted` check — Critical for async code

```dart
class MyWidget extends StatefulWidget { ... }

class _MyWidgetState extends State<MyWidget> {
  @override
  void initState() {
    super.initState();
    _loadData();
  }

  Future<void> _loadData() async {
    await Future.delayed(Duration(seconds: 3));  // User might navigate away

    // ❌ CRASH if widget was disposed!
    setState(() => _data = 'loaded');

    // ✅ Safe
    if (!mounted) return;  // <- ALWAYS check mounted after await
    setState(() => _data = 'loaded');
  }
}
```

#### 18.9 Debugging checklist

When something isn't working:

```
□ Read the error message carefully
□ Look at the file:line in the stack trace
□ Add debugPrint() before the crash to trace execution
□ Check ProviderScope wraps your app
□ Check ref.watch vs ref.read usage
□ Check .notifier when calling methods
□ Check for missing const constructors
□ Check imports (are they correct?)
□ Run flutter pub get (dependencies installed?)
□ Run flutter clean (then rebuild)
□ Restart the app (not just hot reload)
□ Check pubspec.yaml for missing dependencies
□ Check Android/iOS build files if platform-specific errors
```

#### 18.10 Exercise: Debug a broken widget

Here's a widget with bugs. Find and fix them:

```dart
// This widget should show a counter that increments when you tap.
// But it crashes. Why?

class BuggyCounter extends StatefulWidget {
  @override
  State<BuggyCounter> createState() => BuggyCounterState();
}

class BuggyCounterState extends State<BuggyCounter> {
  int count;

  @override
  void initState() {
    count = 0;
    super.initState();  // ← Bug 1: super.initState() should be FIRST
  }

  void increment() {
    count++;  // ← Bug 2: Missing setState()
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: increment,
      child: Text('$count'),
    );
  }
}
```

**Fixes:**
```dart
class FixedCounter extends StatefulWidget {
  @override
  State<FixedCounter> createState() => FixedCounterState();
}

class FixedCounterState extends State<FixedCounter> {
  int count = 0;

  @override
  void initState() {
    super.initState();  // ← Fix 1: super first
  }

  void increment() {
    setState(() => count++);  // ← Fix 2: setState
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: increment,
      child: Text('$count'),
    );
  }
}
```

---

### Chapter 19: State Management with Riverpod

#### 19.1 The problem Riverpod solves

Without Riverpod, each widget manages its own state. When data changes in one widget, others don't know.

```dart
// Screen A: Has its own _unreadCount = 3
// Screen B: Has its own _unreadCount = 3
// When A acknowledges an alert, B still shows 3
```

With Riverpod, state lives in ONE place. All widgets read from the same source.

#### 19.2 Setting up Riverpod

**pubspec.yaml:**
```yaml
dependencies:
  flutter_riverpod: ^3.3.2
```

**main.dart:**
```dart
import 'package:flutter/material.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';

void main() {
  runApp(const ProviderScope(child: MyApp()));
}
```

**`ProviderScope` is REQUIRED.** It's like the electrical panel — without it, nothing works.

#### 19.3 The State class

```dart
class CounterState {
  final int value;
  const CounterState({this.value = 0});

  CounterState copyWith({int? value}) =>
    CounterState(value: value ?? this.value);
}
```

**Rules for state classes:**
- All fields are `final` (immutable)
- Has a `const` constructor
- Has `copyWith` method

#### 19.4 The Notifier class

```dart
class CounterNotifier extends Notifier<CounterState> {
  @override
  CounterState build() => const CounterState();

  void increment() => state = state.copyWith(value: state.value + 1);
  void decrement() => state = state.copyWith(value: state.value - 1);
  void reset() => state = const CounterState();
}
```

**Key points:**
- `extends Notifier<StateType>` — manages state of type StateType
- `build()` — returns initial state, called once
- Methods update state via `state = state.copyWith(...)`
- Never mutate `state` directly — always assign a new object

#### 19.5 The Provider constant

```dart
final counterProvider =
    NotifierProvider<CounterNotifier, CounterState>(() => CounterNotifier());

// Generic parameters: <NotifierClass, StateClass>
```

#### 19.6 Using providers in widgets

```dart
class CounterScreen extends ConsumerWidget {
  const CounterScreen({super.key});

  @override
  Widget build(BuildContext context, WidgetRef ref) {
    // ref.watch → subscribe (widget rebuilds on change)
    final count = ref.watch(counterProvider).value;

    return Scaffold(
      body: Column(
        children: [
          Text('$count', style: TextStyle(fontSize: 48)),
          ElevatedButton(
            onPressed: () {
              // ref.read .notifier → get the controller and call methods
              ref.read(counterProvider.notifier).increment();
            },
            child: Text('+'),
          ),
        ],
      ),
    );
  }
}
```

#### 19.7 The Golden Rule of `ref`

| Context | Use | Why |
|---------|-----|-----|
| Inside `build()` | `ref.watch(provider)` | Subscribe — rebuild on change |
| Inside callbacks | `ref.read(provider.notifier).method()` | One-time action, no rebuild needed |

```dart
// ❌ WRONG — no subscription
final count = ref.read(counterProvider);

// ✅ CORRECT — subscribes to changes
final count = ref.watch(counterProvider);

// ❌ WRONG — calling method on state
ref.read(counterProvider).increment();

// ✅ CORRECT — calling method on notifier
ref.read(counterProvider.notifier).increment();
```

#### 19.8 Two types of providers

**NotifierProvider** — mutable state with methods:

```dart
class CounterNotifier extends Notifier<CounterState> {
  @override
  CounterState build() => const CounterState();
  void increment() => state = state.copyWith(value: state.value + 1);
}
final counterProvider = NotifierProvider<CounterNotifier, CounterState>(() => CounterNotifier());
```

**Provider** — computed/derived values (read-only):

```dart
final doubledProvider = Provider<int>((ref) {
  final count = ref.watch(counterProvider).value;
  return count * 2;
});
```

| | NotifierProvider | Provider |
|---|---|---|
| Has methods? | Yes | No |
| Can change? | Yes | No (auto-computed) |
| `.notifier`? | Yes | No |
| Use case | Filters, toggles, forms | Filtered lists, summaries |

#### 19.9 Provider chains

Providers can depend on other providers:

```dart
// Base provider (mutable)
final searchProvider = NotifierProvider<SearchNotifier, SearchState>(...);

// Derived provider (computed)
final filteredResultsProvider = Provider<List<Result>>((ref) {
  final state = ref.watch(searchProvider);
  return allResults.where((r) => 
    r.name.toLowerCase().contains(state.query.toLowerCase())
  ).toList();
});

// Another derived provider (depends on filtered)
final summaryProvider = Provider<String>((ref) {
  final results = ref.watch(filteredResultsProvider);
  return '${results.length} results found';
});
```

When search changes → `searchProvider` updates → `filteredResultsProvider` recalculates → `summaryProvider` recalculates → widgets rebuild.

#### 19.10 The complete lifecycle

```
1. Widget calls ref.watch(provider)
2. Riverpod checks: does provider exist?
   → No → calls factory, runs build(), stores state
   → Yes → returns existing state
3. User action → ref.read(provider.notifier).method()
4. Notifier: state = state.copyWith(...)
5. Riverpod compares: oldState != newState?
   → Yes → notify ALL watchers
   → No → do nothing
6. All watching widgets rebuild with new state
7. No more watchers? Provider is auto-disposed
8. New watcher appears? Provider is created fresh
```

---

### Chapter 20: Building a Complete App — Todo List

Let's build a complete Todo app from scratch. This demonstrates everything we've learned.

#### 20.1 Project structure

```
lib/
├── main.dart
├── models/
│   ├── todo_model.dart
│   └── todo_state.dart
├── providers/
│   └── todo_provider.dart
├── screens/
│   └── todo_screen.dart
└── data/
    └── todos_list.dart
```

#### 20.2 Entity model (`models/todo_model.dart`)

```dart
class TodoModel {
  final int id;
  final String title;
  final bool isDone;

  const TodoModel({
    required this.id,
    required this.title,
    this.isDone = false,
  });

  TodoModel copyWith({int? id, String? title, bool? isDone}) =>
    TodoModel(id: id ?? this.id, title: title ?? this.title, isDone: isDone ?? this.isDone);
}
```

#### 20.3 State model (`models/todo_state.dart`)

```dart
import 'todo_model.dart';

class TodoState {
  final String filter;
  final String search;
  final List<TodoModel> todos;

  const TodoState({
    this.filter = 'All',
    this.search = '',
    this.todos = const [],
  });

  TodoState copyWith({String? filter, String? search, List<TodoModel>? todos}) =>
    TodoState(filter: filter ?? this.filter, search: search ?? this.search, todos: todos ?? this.todos);
}
```

#### 20.4 Mock data (`data/todos_list.dart`)

```dart
import '../models/todo_model.dart';

final List<TodoModel> todoList = [
  TodoModel(id: 1, title: 'Learn Dart basics'),
  TodoModel(id: 2, title: 'Learn Flutter widgets'),
  TodoModel(id: 3, title: 'Build a Todo app', isDone: true),
  TodoModel(id: 4, title: 'Learn Riverpod'),
  TodoModel(id: 5, title: 'Publish the app'),
];
```

#### 20.5 Provider (`providers/todo_provider.dart`)

```dart
import 'package:flutter_riverpod/flutter_riverpod.dart';
import '../models/todo_model.dart';
import '../models/todo_state.dart';
import '../data/todos_list.dart';

class TodoNotifier extends Notifier<TodoState> {
  @override
  TodoState build() => TodoState(todos: todoList.map((t) => t.copyWith()).toList());

  void setFilter(String f) => state = state.copyWith(filter: f);

  void setSearch(String q) => state = state.copyWith(search: q);

  void toggleTodo(int id) {
    state = state.copyWith(
      todos: state.todos.map((t) {
        if (t.id == id) return t.copyWith(isDone: !t.isDone);
        return t;
      }).toList(),
    );
  }

  void addTodo(String title) {
    if (title.trim().isEmpty) return;
    final todo = TodoModel(id: DateTime.now().millisecondsSinceEpoch, title: title.trim());
    state = state.copyWith(todos: [...state.todos, todo]);
  }

  void deleteTodo(int id) {
    state = state.copyWith(
      todos: state.todos.where((t) => t.id != id).toList(),
    );
  }

  List<TodoModel> get filteredTodos {
    return state.todos.where((t) {
      // Apply search
      if (state.search.isNotEmpty &&
          !t.title.toLowerCase().contains(state.search.toLowerCase())) {
        return false;
      }
      // Apply filter
      if (state.filter == 'Done') return t.isDone;
      if (state.filter == 'Pending') return !t.isDone;
      return true; // 'All'
    }).toList();
  }

  int get pendingCount => state.todos.where((t) => !t.isDone).length;
  int get doneCount => state.todos.where((t) => t.isDone).length;
}

final todoProvider = NotifierProvider<TodoNotifier, TodoState>(() => TodoNotifier());
```

#### 20.6 Screen (`screens/todo_screen.dart`)

```dart
import 'package:flutter/material.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import '../providers/todo_provider.dart';

class TodoScreen extends ConsumerWidget {
  const TodoScreen({super.key});

  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final notifier = ref.read(todoProvider.notifier);
    final state = ref.watch(todoProvider);
    final todos = notifier.filteredTodos;

    return Scaffold(
      appBar: AppBar(
        title: Text('Todos (${notifier.pendingCount} pending)'),
        actions: [
          PopupMenuButton<String>(
            onSelected: (f) => notifier.setFilter(f),
            icon: Icon(Icons.filter_list),
            itemBuilder: (_) => [
              CheckedPopupMenuItem(
                value: 'All',
                checked: state.filter == 'All',
                child: Text('All'),
              ),
              CheckedPopupMenuItem(
                value: 'Pending',
                checked: state.filter == 'Pending',
                child: Text('Pending'),
              ),
              CheckedPopupMenuItem(
                value: 'Done',
                checked: state.filter == 'Done',
                child: Text('Done'),
              ),
            ],
          ),
        ],
      ),
      body: Column(
        children: [
          // Search bar
          Padding(
            padding: const EdgeInsets.all(16),
            child: TextField(
              decoration: InputDecoration(
                hintText: 'Search todos...',
                prefixIcon: Icon(Icons.search),
                border: OutlineInputBorder(),
                suffixIcon: state.search.isNotEmpty
                    ? IconButton(
                        icon: Icon(Icons.clear),
                        onPressed: () => notifier.setSearch(''),
                      )
                    : null,
              ),
              onChanged: (v) => notifier.setSearch(v),
            ),
          ),

          // Stats row
          Padding(
            padding: EdgeInsets.symmetric(horizontal: 16),
            child: Row(
              children: [
                Text('Total: ${state.todos.length}'),
                SizedBox(width: 16),
                Text('Done: ${notifier.doneCount}'),
                SizedBox(width: 16),
                Text('Pending: ${notifier.pendingCount}'),
              ],
            ),
          ),
          SizedBox(height: 8),

          // Todo list
          Expanded(
            child: todos.isEmpty
                ? Center(
                    child: Column(
                      mainAxisAlignment: MainAxisAlignment.center,
                      children: [
                        Icon(Icons.task_alt, size: 64, color: Colors.grey),
                        SizedBox(height: 16),
                        Text('No todos found',
                            style: TextStyle(fontSize: 18, color: Colors.grey)),
                      ],
                    ),
                  )
                : ListView.builder(
                    itemCount: todos.length,
                    itemBuilder: (ctx, i) {
                      final todo = todos[i];
                      return Dismissible(
                        key: Key(todo.id.toString()),
                        direction: DismissDirection.endToStart,
                        background: Container(
                          color: Colors.red,
                          alignment: Alignment.centerRight,
                          padding: EdgeInsets.only(right: 16),
                          child: Icon(Icons.delete, color: Colors.white),
                        ),
                        onDismissed: (_) => notifier.deleteTodo(todo.id),
                        child: ListTile(
                          leading: Checkbox(
                            value: todo.isDone,
                            onChanged: (_) => notifier.toggleTodo(todo.id),
                          ),
                          title: Text(
                            todo.title,
                            style: TextStyle(
                              decoration: todo.isDone
                                  ? TextDecoration.lineThrough
                                  : null,
                              color: todo.isDone ? Colors.grey : null,
                            ),
                          ),
                          trailing: IconButton(
                            icon: Icon(Icons.delete_outline, color: Colors.red),
                            onPressed: () => notifier.deleteTodo(todo.id),
                          ),
                        ),
                      );
                    },
                  ),
          ),
        ],
      ),
      floatingActionButton: FloatingActionButton.extended(
        onPressed: () => _showAddDialog(context, ref),
        icon: Icon(Icons.add),
        label: Text('Add Todo'),
      ),
    );
  }

  void _showAddDialog(BuildContext context, WidgetRef ref) {
    final controller = TextEditingController();
    showDialog(
      context: context,
      builder: (ctx) => AlertDialog(
        title: Text('New Todo'),
        content: TextField(
          controller: controller,
          autofocus: true,
          decoration: InputDecoration(hintText: 'What needs to be done?'),
          onSubmitted: (v) {
            if (v.trim().isNotEmpty) {
              ref.read(todoProvider.notifier).addTodo(v);
              Navigator.pop(ctx);
            }
          },
        ),
        actions: [
          TextButton(
            onPressed: () => Navigator.pop(ctx),
            child: Text('Cancel'),
          ),
          ElevatedButton(
            onPressed: () {
              if (controller.text.trim().isNotEmpty) {
                ref.read(todoProvider.notifier).addTodo(controller.text);
                Navigator.pop(ctx);
              }
            },
            child: Text('Add'),
          ),
        ],
      ),
    );
  }
}
```

#### 20.7 Entry point (`main.dart`)

```dart
import 'package:flutter/material.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import 'screens/todo_screen.dart';

void main() {
  runApp(const ProviderScope(child: TodoApp()));
}

class TodoApp extends StatelessWidget {
  const TodoApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Todo App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        useMaterial3: true,
      ),
      home: const TodoScreen(),
    );
  }
}
```

---

### Chapter 21: App Architecture — Organizing Code for Real Projects

#### 21.1 The problem: Spaghetti code

When you start a project, everything is simple. But as the app grows, code gets messy:

```
lib/
├── main.dart           ← Has database code, auth code, UI code, ALL MIXED
├── todo_screen.dart    ← 500 lines: UI + logic + API calls + navigation
└── todo_card.dart      ← Also has some logic copied from todo_screen
```

This is **spaghetti code** — everything tangled together. It causes:
- Hard to find anything
- Fixing one bug creates another
- Can't reuse code
- New developers can't understand it

**Analogy:** A toolbox where you throw all tools in one drawer vs. a toolbox with separate compartments. Which is easier to work with?

#### 21.2 The solution: Separate responsibilities

A well-organized Flutter app separates code into **layers**:

```
┌─────────────────────────────────┐
│         UI Layer (Screens)      │  ← What users see
│   StatelessWidget/ConsumerWidget │
├─────────────────────────────────┤
│    State Layer (Providers)      │  ← App state & logic
│   Notifier / ChangeNotifier     │
├─────────────────────────────────┤
│   Repository Layer (Services)   │  ← Data access & business logic
│   Repository classes            │
├─────────────────────────────────┤
│     Data Layer (Sources)        │  ← Where data comes from
│   API / Database / SharedPrefs  │
└─────────────────────────────────┘
```

**Key rule:** Each layer only talks to the layer directly below it.
- Screen → Provider (read state, call methods)
- Provider → Repository (get/save data)
- Repository → API or Database (actual I/O)

#### 21.3 The Repository Pattern

**What is a repository?** A class that hides WHERE data comes from. The screen doesn't know if data is from Firebase, SQLite, or a file — it just calls `repository.getTodos()`.

```dart
// 1. Define an abstract interface (contract)
abstract class TodoRepository {
  Future<List<TodoModel>> getTodos();
  Future<void> addTodo(String title);
  Future<void> toggleTodo(String id);
  Future<void> deleteTodo(String id);
}

// 2. Implement for Firebase
class FirebaseTodoRepository implements TodoRepository {
  final _firestore = FirebaseFirestore.instance;

  @override
  Future<List<TodoModel>> getTodos() async {
    final snapshot = await _firestore.collection('todos').get();
    return snapshot.docs.map((doc) => TodoModel.fromFirestore(doc)).toList();
  }

  @override
  Future<void> addTodo(String title) async {
    await _firestore.collection('todos').add({
      'title': title,
      'isDone': false,
      'createdAt': FieldValue.serverTimestamp(),
    });
  }

  @override
  Future<void> toggleTodo(String id) async { /* ... */ }

  @override
  Future<void> deleteTodo(String id) async { /* ... */ }
}

// 3. Implement for Local Storage
class LocalTodoRepository implements TodoRepository {
  @override
  Future<List<TodoModel>> getTodos() async {
    // Read from local JSON file
    // ...
  }

  @override
  Future<void> addTodo(String title) async {
    // Write to local JSON file
    // ...
  }
  // ... etc
}

// 4. Provider uses the interface, NOT the implementation
class TodoNotifier extends Notifier<TodoState> {
  // The repository is injected — not hardcoded
  final TodoRepository repository;

  TodoNotifier(this.repository);

  @override
  TodoState build() => const TodoState();

  Future<void> loadTodos() async {
    final todos = await repository.getTodos();
    state = state.copyWith(todos: todos);
  }

  Future<void> addTodo(String title) async {
    await repository.addTodo(title);
    await loadTodos();
  }
}
```

**Benefits of the repository pattern:**
- **Switch backends easily** — change one line, not every screen
- **Test with mock data** — test your app without Firebase
- **Single source of truth** — all data access goes through repository

#### 21.4 Dependency Injection — Providing dependencies

```dart
// 1. Create a Provider for the repository
final todoRepositoryProvider = Provider<TodoRepository>((ref) {
  // Change this ONE line to switch backends:
  return FirebaseTodoRepository();
  // return LocalTodoRepository();     // Switch to local
  // return SupabaseTodoRepository();  // Switch to Supabase
});

// 2. Notifier receives repository via ref
final todoListProvider = NotifierProvider<TodoNotifier, TodoState>(
  () => TodoNotifier(ref.read(todoRepositoryProvider)),
  // But wait — ref isn't available at top level!
);

// Solution: use a factory function
final todoListProvider = NotifierProvider<TodoNotifier, TodoState>(
  () => TodoNotifier(todoRepositoryProvider),
);

// But Notifier can't receive ref directly at top level...

// Best solution — use Riverpod's ref inside the notifier:
class TodoNotifier extends Notifier<TodoState> {
  TodoRepository get _repository => ref.read(todoRepositoryProvider);

  @override
  TodoState build() => const TodoState();

  Future<void> loadTodos() async {
    final todos = await _repository.getTodos();
    state = state.copyWith(todos: todos);
  }
}
```

**Key insight:** With Riverpod, you can access other providers INSIDE your notifier via `ref.read()` or `ref.watch()`. This IS dependency injection — Riverpod handles it for you.

#### 21.5 Service classes

Services handle specific concerns that don't fit in a repository:

```dart
// Navigation service — centralize navigation logic
class NavigationService {
  final GoRouter _router;

  NavigationService(this._router);

  void goToHome() => _router.go('/home');
  void goToLogin() => _router.go('/login');
  void goToProfile(String id) => _router.go('/profile/$id');
  void goBack() => _router.pop();

  // Conditional navigation (useful for auth redirect)
  void handleAuthState(User? user) {
    if (user != null) {
      goToHome();
    } else {
      goToLogin();
    }
  }
}

// Logger service — centralize logging
class LoggerService {
  void info(String message) => debugPrint('[INFO] $message');
  void warning(String message) => debugPrint('[WARN] $message');
  void error(String message, [Object? exception]) {
    debugPrint('[ERROR] $message');
    if (exception != null) debugPrint('  Cause: $exception');
  }
}

// Analytics service — track user actions
class AnalyticsService {
  void logEvent(String name, {Map<String, dynamic>? properties}) {
    // Firebase Analytics, Mixpanel, or custom
    // debugPrint('[Analytics] $name');
  }

  void logScreen(String screenName) {
    logEvent('screen_view', properties: {'screen': screenName});
  }
}
```

#### 21.6 Error handling strategy

```dart
// 1. Define a Result type (success or failure)
sealed class Result<T> {
  const Result();
}

class Success<T> extends Result<T> {
  final T data;
  const Success(this.data);
}

class Failure<T> extends Result<T> {
  final String message;
  final Object? exception;
  const Failure(this.message, {this.exception});
}

// 2. Repository returns Result, not raw data
class TodoRepositoryImpl implements TodoRepository {
  @override
  Future<Result<List<TodoModel>>> getTodos() async {
    try {
      final todos = await _api.fetchTodos();
      return Success(todos);
    } on SocketException {
      return Failure('No internet connection');
    } on HttpException catch (e) {
      return Failure('Server error: ${e.message}');
    } catch (e) {
      return Failure('Unknown error', exception: e);
    }
  }
}

// 3. Notifier handles Result
class TodoNotifier extends Notifier<TodoState> {
  @override
  TodoState build() => const TodoState();

  Future<void> loadTodos() async {
    state = state.copyWith(loading: true, error: null);

    final result = await ref.read(todoRepositoryProvider).getTodos();

    switch (result) {
      case Success(data: final todos):
        state = state.copyWith(loading: false, todos: todos);
      case Failure(message: final message):
        state = state.copyWith(loading: false, error: message);
    }
  }
}

// 4. Screen shows appropriate UI
final state = ref.watch(todoListProvider);
if (state.loading) return CircularProgressIndicator();
if (state.error != null) return ErrorWidget(state.error!, () => ref.read(...).loadTodos());
return ListView(...);
```

#### 21.7 Folder structure for large projects

```
lib/
├── main.dart                          # Entry point
├── app.dart                           # MaterialApp + ProviderScope
├── core/                              # Shared code
│   ├── theme/
│   │   └── app_theme.dart             # ThemeData definitions
│   ├── constants/
│   │   └── constants.dart             # App-wide constants
│   ├── services/
│   │   ├── navigation_service.dart    # GoRouter config
│   │   ├── logger_service.dart        # Logging
│   │   └── analytics_service.dart     # Analytics
│   └── network/
│       ├── api_client.dart            # HTTP client (Dio/Http)
│       └── api_exceptions.dart        # Custom exceptions
│
├── features/                          # Feature-based organization
│   ├── auth/
│   │   ├── models/
│   │   │   └── user_model.dart
│   │   ├── providers/
│   │   │   └── auth_provider.dart
│   │   ├── repositories/
│   │   │   └── auth_repository.dart
│   │   └── screens/
│   │       ├── login_screen.dart
│   │       └── register_screen.dart
│   │
│   └── todos/
│       ├── models/
│       │   └── todo_model.dart
│       ├── providers/
│       │   └── todo_provider.dart
│       ├── repositories/
│       │   └── todo_repository.dart
│       └── screens/
│           ├── todo_list_screen.dart
│           └── todo_detail_screen.dart
│
└── shared/                            # Reusable widgets
    ├── widgets/
    │   ├── loading_widget.dart
    │   ├── error_widget.dart
    │   └── empty_state_widget.dart
    └── extensions/
        └── context_extensions.dart
```

**Feature-based organization** groups all files for a feature together. This is better than grouping by type (models/, screens/, providers/) because:
- Related files are next to each other
- Easy to find everything for "auth"
- Easy to remove a feature (delete one folder)
- Scales to 100+ files

#### 21.8 The Service Locator pattern (alternative)

```dart
// A simple service locator (not recommended for large apps)
class Locator {
  static final Map<Type, dynamic> _services = {};

  static T register<T>(T service) {
    _services[T] = service;
    return service;
  }

  static T get<T>() => _services[T] as T;
}

// Register at app start
void setupLocator() {
  Locator.register<LoggerService>(LoggerService());
  Locator.register<TodoRepository>(FirebaseTodoRepository());
}

// Use anywhere
final repo = Locator.get<TodoRepository>();
```

**Service Locator vs Riverpod DI:**
| | Service Locator | Riverpod (ref.read) |
|---|----------------|---------------------|
| How it works | Global registry | Provider hierarchy |
| Testability | Harder (can't easily swap) | Easy (Provider overrides) |
| Lifecycle | Manual | Auto-dispose |
| Recommended? | For very simple apps | For all Flutter apps |

**Riverpod IS your dependency injection.** Don't use a separate DI system — Riverpod handles it better.

#### 21.9 Exercise: Refactor the Todo App

Take the Todo app from Chapter 20 and:
1. Create a `TodoRepository` interface
2. Create a `LocalTodoRepository` implementation (using file I/O)
3. Create a `FirebaseTodoRepository` implementation (using Cloud Firestore)
4. Update `TodoNotifier` to use the repository via `ref.read`
5. Add error handling with the `Result` type
6. Verify you can switch backends by changing one line

```dart
// The notifier becomes simpler and more testable:
class RefactoredTodoNotifier extends Notifier<TodoState> {
  @override
  TodoState build() => const TodoState();

  Future<void> loadTodos() async {
    state = state.copyWith(loading: true);
    final result = await ref.read(todoRepositoryProvider).getTodos();
    switch (result) {
      case Success(data: final todos):
        state = state.copyWith(loading: false, todos: todos);
      case Failure(message: final msg):
        state = state.copyWith(loading: false, error: msg);
    }
  }
}
```

---

### Chapter 23: Local Storage — Saving Data on the Device

#### 23.1 What is data persistence?

When you close an app and open it again, where did all the data go?

```
App opens → Data in memory → App closes → Data GONE ❌
App opens → Data in storage → App closes → Data still there ✅
```

**Memory (RAM):** Fast but temporary. When the app closes, everything is erased.
**Storage (disk):** Slower but permanent. Data survives app restarts and phone reboots.

**Analogy:** Memory is your desk — you work on papers there. Storage is your filing cabinet — you put things there for later.

#### 23.2 Types of local storage

| Method | What it stores | Speed | Complexity |
|--------|---------------|-------|------------|
| **SharedPreferences** | Small key-value data (settings, tokens) | Fast | Very simple |
| **File I/O** | Files (images, documents, JSON) | Medium | Simple |
| **SQLite (drift)** | Structured data (tables, queries) | Fast | Medium |
| **Hive/Isar** | NoSQL database for Dart objects | Very fast | Medium |

**Rule of thumb:**
- User settings/preferences → SharedPreferences
- Images/files → File storage
- Lists of data (todos, contacts) → SQLite or Hive
- Complex queries/relationships → SQLite

#### 23.3 SharedPreferences — Settings & Preferences

**What it is:** Stores simple data as key-value pairs. Like a JSON object that lives on your phone.

**Setup:**
```yaml
dependencies:
  shared_preferences: ^2.2.2
```

**Basic usage:**
```dart
import 'package:shared_preferences/shared_preferences.dart';

// SAVE data
Future<void> saveUserName(String name) async {
  final prefs = await SharedPreferences.getInstance();
  await prefs.setString('user_name', name);
  //           ^ Method    ^ Key       ^ Value
  // Other methods: setInt, setBool, setDouble, setStringList
}

// READ data
Future<String?> loadUserName() async {
  final prefs = await SharedPreferences.getInstance();
  return prefs.getString('user_name');
  // Returns null if key doesn't exist
}

// DELETE data
Future<void> removeUserName() async {
  final prefs = await SharedPreferences.getInstance();
  await prefs.remove('user_name');
}
```

**Data types you can store:**
```dart
await prefs.setString('name', 'Alice');         // Text
await prefs.setInt('age', 30);                   // Whole number
await prefs.setDouble('price', 99.99);           // Decimal
await prefs.setBool('darkMode', true);           // True/false
await prefs.setStringList('tags', ['a', 'b']);   // List of strings

// Reading back:
String? name = prefs.getString('name');
int? age = prefs.getInt('age');
double? price = prefs.getDouble('price');
bool? darkMode = prefs.getBool('darkMode');
List<String>? tags = prefs.getStringList('tags');
```

**Real example — Theme settings:**
```dart
class SettingsNotifier extends Notifier<SettingsState> {
  @override
  SettingsState build() {
    // Load from SharedPreferences when app starts
    return SettingsState(
      darkMode: _loadDarkMode(),
      fontSize: _loadFontSize(),
    );
  }

  bool _loadDarkMode() {
    // Must be synchronous here — we use a hack
    return false; // Simplified; real code uses async loading in init
  }

  void toggleDarkMode() async {
    final newValue = !state.darkMode;
    state = state.copyWith(darkMode: newValue);

    // Save to device
    final prefs = await SharedPreferences.getInstance();
    await prefs.setBool('dark_mode', newValue);
  }
}
```

**Common mistake:**
```dart
// ❌ Calling getInstance inside build() — creates new instance every rebuild
@override
Widget build(context) {
  final prefs = await SharedPreferences.getInstance(); // ERROR! build can't be async
}

// ✅ Load once when app starts, store in provider
```

#### 23.4 File I/O — Reading & Writing Files

**What it is:** Save any data as files on the device. Used for images, JSON exports, documents.

**Setup:**
```yaml
dependencies:
  path_provider: ^2.1.2  # Gives you the correct folder paths
```

**Getting the right folder:**
```dart
import 'package:path_provider/path_provider.dart';
import 'dart:io';

Future<void> example() async {
  // Documents directory — for user-generated content
  final docsDir = await getApplicationDocumentsDirectory();
  // Android: /data/data/com.example.app/app_flutter/
  // iOS: /var/mobile/Containers/Data/Application/.../Documents/

  // Temporary directory — files can be deleted anytime
  final tempDir = await getTemporaryDirectory();

  // External storage (Android only) — shared with other apps
  final extDir = await getExternalStorageDirectory();
}
```

**Writing and reading text files:**
```dart
Future<void> saveNote(String title, String content) async {
  final dir = await getApplicationDocumentsDirectory();
  final file = File('${dir.path}/notes/$title.txt');

  // Create directories if they don't exist
  await file.parent.create(recursive: true);

  // Write to file
  await file.writeAsString(content);
}

Future<String?> loadNote(String title) async {
  final dir = await getApplicationDocumentsDirectory();
  final file = File('${dir.path}/notes/$title.txt');

  if (await file.exists()) {
    return await file.readAsString();
  }
  return null; // File doesn't exist
}
```

**Saving a list of objects as JSON:**
```dart
import 'dart:convert';

// Save todo list to a JSON file
Future<void> saveTodos(List<TodoModel> todos) async {
  final dir = await getApplicationDocumentsDirectory();
  final file = File('${dir.path}/todos.json');

  // Convert each TodoModel to a Map, then to JSON string
  final List<Map<String, dynamic>> jsonList = todos
    .map((t) => t.toJson())
    .toList();

  await file.writeAsString(jsonEncode(jsonList));
}

// Load todo list from JSON file
Future<List<TodoModel>> loadTodos() async {
  final dir = await getApplicationDocumentsDirectory();
  final file = File('${dir.path}/todos.json');

  if (!await file.exists()) return [];

  final String content = await file.readAsString();
  final List<dynamic> jsonList = jsonDecode(content);

  return jsonList
    .map((j) => TodoModel.fromJson(j as Map<String, dynamic>))
    .toList();
}
```

**Key file operations:**
```dart
final file = File('path/to/file.txt');

await file.writeAsString('content');     // Write text
await file.writeAsBytes(bytes);          // Write binary (images)
String content = await file.readAsString(); // Read text
List<int> bytes = await file.readAsBytes(); // Read binary
bool exists = await file.exists();       // Check if exists
await file.delete();                     // Delete the file
int size = await file.length();          // File size in bytes
```

#### 23.5 SQLite with `sqflite` — Structured Data

**What is SQLite?** A database that lives in a single file on your phone. It stores data in **tables** (like Excel spreadsheets).

```
SQLite Database (todos.db)
┌──────────────────────────────────────────┐
│  todos table                             │
├────┬──────────┬──────────┬───────────────┤
│ id │ title    │ is_done  │ created_at    │
├────┼──────────┼──────────┼───────────────┤
│ 1  │ Buy milk │ 0        │ 2024-01-15    │
│ 2  │ Study    │ 1        │ 2024-01-14    │
│ 3  │ Exercise │ 0        │ 2024-01-15    │
└────┴──────────┴──────────┴───────────────┘
```

**Setup:**
```yaml
dependencies:
  sqflite: ^2.3.2
  path: ^1.9.0  # For joining paths
```

**Creating the database:**
```dart
import 'package:sqflite/sqflite.dart';
import 'package:path/path.dart';

class DatabaseHelper {
  static Database? _database;

  static Future<Database> get database async {
    if (_database != null) return _database!;
    _database = await _initDatabase();
    return _database!;
  }

  static Future<Database> _initDatabase() async {
    final dbPath = await getDatabasesPath();
    final path = join(dbPath, 'my_app.db');

    return await openDatabase(
      path,
      version: 1,
      onCreate: (db, version) async {
        // Create tables when database is first created
        await db.execute('''
          CREATE TABLE todos (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            title TEXT NOT NULL,
            is_done INTEGER DEFAULT 0,
            created_at TEXT NOT NULL
          )
        ''');
      },
      onUpgrade: (db, oldVersion, newVersion) async {
        // Handle database schema changes (for app updates)
      },
    );
  }
}
```

**CRUD operations (Create, Read, Update, Delete):**
```dart
class TodoRepository {
  // CREATE — insert a new todo
  Future<int> addTodo(String title) async {
    final db = await DatabaseHelper.database;
    return await db.insert('todos', {
      'title': title,
      'is_done': 0,
      'created_at': DateTime.now().toIso8601String(),
    });
    // Returns the id of the new row
  }

  // READ — get all todos
  Future<List<Map<String, dynamic>>> getTodos() async {
    final db = await DatabaseHelper.database;
    return await db.query(
      'todos',
      orderBy: 'created_at DESC',  // Newest first
    );
    // Returns a list of maps: [{id: 1, title: '...', is_done: 0, ...}, ...]
  }

  // READ — get a single todo
  Future<Map<String, dynamic>?> getTodo(int id) async {
    final db = await DatabaseHelper.database;
    final results = await db.query('todos', where: 'id = ?', whereArgs: [id]);
    return results.isNotEmpty ? results.first : null;
  }

  // UPDATE — toggle done status
  Future<void> toggleTodo(int id) async {
    final db = await DatabaseHelper.database;
    await db.rawUpdate(
      'UPDATE todos SET is_done = CASE WHEN is_done = 0 THEN 1 ELSE 0 END WHERE id = ?',
      [id],
    );
  }

  // DELETE — remove a todo
  Future<void> deleteTodo(int id) async {
    final db = await DatabaseHelper.database;
    await db.delete('todos', where: 'id = ?', whereArgs: [id]);
  }

  // DELETE — remove all done todos
  Future<void> clearDone() async {
    final db = await DatabaseHelper.database;
    await db.delete('todos', where: 'is_done = ?', whereArgs: [1]);
  }
}
```

**SQLite + Riverpod integration:**
```dart
class TodoDbNotifier extends Notifier<List<TodoModel>> {
  final TodoRepository _repo = TodoRepository();

  @override
  List<TodoModel> build() {
    // Load from database when provider is first used
    _loadTodos();
    return [];
  }

  Future<void> _loadTodos() async {
    final maps = await _repo.getTodos();
    state = maps.map((m) => TodoModel.fromDbMap(m)).toList();
  }

  Future<void> addTodo(String title) async {
    await _repo.addTodo(title);
    await _loadTodos();  // Refresh list from DB
  }

  Future<void> toggleTodo(int id) async {
    await _repo.toggleTodo(id);
    await _loadTodos();
  }

  Future<void> deleteTodo(int id) async {
    await _repo.deleteTodo(id);
    await _loadTodos();
  }
}
```

**SQLite query cheat sheet:**
```dart
// All rows
await db.query('todos');

// Filtered
await db.query('todos', where: 'is_done = ?', whereArgs: [1]);

// Ordered
await db.query('todos', orderBy: 'title ASC');

// Limited
await db.query('todos', limit: 10);

// With LIKE (search)
await db.query('todos', where: 'title LIKE ?', whereArgs: ['%search%']);

// Raw SQL (for complex queries)
await db.rawQuery('SELECT * FROM todos WHERE is_done = 1 ORDER BY created_at DESC');

// Count
final count = Sqflite.firstIntValue(
  await db.rawQuery('SELECT COUNT(*) FROM todos'),
);
```

#### 23.6 Hive — Fast NoSQL Database

**What is Hive?** A lightweight, fast NoSQL database for Dart. Stores Dart objects directly without JSON conversion.

**Setup:**
```yaml
dependencies:
  hive: ^2.2.3
  hive_flutter: ^1.1.0  # Flutter-specific initialization

dev_dependencies:
  hive_generator: ^2.0.1
  build_runner: ^2.4.8
```

**Basic usage:**
```dart
import 'package:hive_flutter/hive_flutter.dart';

void main() async {
  // Initialize Hive
  await Hive.initFlutter();

  // Register adapters (for type adapters — needed for objects)
  Hive.registerAdapter(TodoModelAdapter());

  // Open a box (like a table)
  await Hive.openBox<TodoModel>('todos');

  runApp(const MyApp());
}

// Using a box:
final box = Hive.box<TodoModel>('todos');

// Add item
await box.add(TodoModel(title: 'Learn Hive'));

// Get all items
final todos = box.values.toList();

// Get by key
final todo = box.get('my-key');

// Update
await box.put('my-key', updatedTodo);

// Delete
await box.delete('my-key');

// Listen to changes (real-time)
box.watch().listen((event) {
  print('Box changed: ${event.key}');
});
```

**Type adapters (for storing objects):**
```dart
// 1. Annotate your model
@HiveType(typeId: 0)
class TodoModel extends HiveObject {
  @HiveField(0)
  final String title;

  @HiveField(1)
  final bool isDone;

  TodoModel({required this.title, this.isDone = false});
}

// 2. Run build_runner to generate adapter
// flutter pub run build_runner build

// 3. Register adapter
Hive.registerAdapter(TodoModelAdapter());
```

#### 23.7 Which one should you use?

| Scenario | Best choice |
|----------|-------------|
| User prefers dark mode | SharedPreferences |
| Remember login token | SharedPreferences |
| Save 50 todo items | SQLite or Hive |
| Save photos offline | File I/O |
| Search/filter data | SQLite (SQL queries) |
| Real-time sync with server | Hive (good for caching) |
| Complex relationships | SQLite (JOIN queries) |
| Simple key-value cache | SharedPreferences |

#### 23.8 Exercise: Build a persistence layer

Add save/load functionality to the Todo app from Chapter 20:

```dart
// 1. Add toJson/fromJson to TodoModel
class TodoModel {
  // ...existing fields...

  Map<String, dynamic> toJson() => {
    'id': id,
    'title': title,
    'isDone': isDone,
  };

  factory TodoModel.fromJson(Map<String, dynamic> json) => TodoModel(
    id: json['id'] as int,
    title: json['title'] as String,
    isDone: json['isDone'] as bool,
  );
}

// 2. In TodoNotifier, load from file on startup
@override
TodoState build() {
  _loadFromDisk();
  return const TodoState();
}

Future<void> _loadFromDisk() async {
  final dir = await getApplicationDocumentsDirectory();
  final file = File('${dir.path}/todos.json');
  if (await file.exists()) {
    final json = await file.readAsString();
    final list = (jsonDecode(json) as List)
      .map((j) => TodoModel.fromJson(j))
      .toList();
    state = state.copyWith(todos: list);
  }
}

// 3. Save after every change
Future<void> _saveToDisk() async {
  final dir = await getApplicationDocumentsDirectory();
  final file = File('${dir.path}/todos.json');
  final json = jsonEncode(state.todos.map((t) => t.toJson()).toList());
  await file.writeAsString(json);
}
```

---

### Chapter 25: Firebase — Google's App Backend

#### 25.1 What is Firebase?

Firebase is a collection of backend services provided by Google. Instead of building your own server, Firebase gives you:

```
Your App
  │
  ├── Firebase Auth → Let users sign in
  ├── Cloud Firestore → Save & query data
  ├── Firebase Storage → Upload images/files
  ├── Firebase Messaging → Push notifications
  └──还有很多 (and more)
```

**Analogy:** Building an app without Firebase is like building a house AND the power plant. Firebase is like plugging into the existing power grid — you focus on the house (your app), Firebase handles the infrastructure.

**Key Firebase services:**
| Service | What it does |
|---------|-------------|
| **Firebase Auth** | User sign-in (email, Google, Apple, phone) |
| **Cloud Firestore** | NoSQL database (stores data as documents) |
| **Firebase Storage** | File/image upload and serving |
| **Cloud Messaging** | Push notifications |
| **Firebase Analytics** | User behavior tracking |
| **Firebase Hosting** | Host your web app |

#### 25.2 Setting up Firebase

**Step 1: Create a Firebase project**
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Click "Create a project"
3. Enter your app name (e.g., "My Todo App")
4. Disable Google Analytics (for now)
5. Click "Create project"

**Step 2: Register your app with Firebase**
1. In the Firebase console, click the Android icon
2. Enter your Android package name (from `android/app/build.gradle`: `applicationId`)
3. Download `google-services.json`
4. Place it in `android/app/` folder

**Step 3: Add Firebase to Flutter**
```yaml
dependencies:
  firebase_core: ^2.27.0         # Required for all Firebase services
  firebase_auth: ^4.18.0         # Authentication
  cloud_firestore: ^4.15.0       # Database
  firebase_storage: ^11.6.0      # File storage
```

**Step 4: Initialize Firebase**
```dart
import 'package:flutter/material.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import 'package:firebase_core/firebase_core.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();  // Required before Firebase
  await Firebase.initializeApp();            // Initialize Firebase
  runApp(const ProviderScope(child: MyApp()));
}
```

#### 25.3 Firebase Auth — Let Users Sign In

**What is authentication?** Proving who you are. Like showing your ID card at the airport.

```
App                     Firebase Auth
 │                          │
 │── "Sign in with email" → │
 │   email: a@b.com        │
 │   password: 123456      │
 │                          │
 │←── User ID + Token ────│  ← "This person is real"
 │                          │
 │── "Get my data" with ──→│
 │   token                  │  ← "I know who this is"
```

**Email/Password sign-in:**
```dart
import 'package:firebase_auth/firebase_auth.dart';

class AuthService {
  final FirebaseAuth _auth = FirebaseAuth.instance;

  // Sign up (create new account)
  Future<User?> signUp(String email, String password) async {
    try {
      final result = await _auth.createUserWithEmailAndPassword(
        email: email,
        password: password,
      );
      return result.user;
    } on FirebaseAuthException catch (e) {
      // Handle specific errors
      if (e.code == 'email-already-in-use') {
        throw Exception('This email is already registered');
      } else if (e.code == 'weak-password') {
        throw Exception('Password must be at least 6 characters');
      }
      throw Exception('Sign up failed: ${e.message}');
    }
  }

  // Sign in (existing account)
  Future<User?> signIn(String email, String password) async {
    try {
      final result = await _auth.signInWithEmailAndPassword(
        email: email,
        password: password,
      );
      return result.user;
    } on FirebaseAuthException catch (e) {
      if (e.code == 'user-not-found') {
        throw Exception('No account found with this email');
      } else if (e.code == 'wrong-password') {
        throw Exception('Wrong password');
      } else if (e.code == 'invalid-credential') {
        throw Exception('Invalid email or password');
      }
      throw Exception('Sign in failed: ${e.message}');
    }
  }

  // Sign out
  Future<void> signOut() async {
    await _auth.signOut();
  }

  // Check if user is signed in
  User? get currentUser => _auth.currentUser;

  // Listen to auth state changes
  Stream<User?> get authState => _auth.authStateChanges();
  // This stream fires when user signs in/out — perfect for Riverpod
}
```

**Auth state with Riverpod:**
```dart
// Provider that watches authentication state
final authStateProvider = StreamProvider<User?>((ref) {
  return FirebaseAuth.instance.authStateChanges();
});

// In your widget:
class HomeScreen extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final authState = ref.watch(authStateProvider);

    return authState.when(
      loading: () => SplashScreen(),          // Checking auth
      data: (user) => user != null             // Signed in
          ? TodoScreen()
          : LoginScreen(),                     // Not signed in
      error: (e, _) => Text('Error: $e'),
    );
  }
}
```

**StreamProvider vs NotifierProvider:**
| Provider type | When to use |
|--------------|-------------|
| `StreamProvider` | When Firebase gives you a Stream (auth state, realtime data) |
| `NotifierProvider` | When you manage state manually (form data, UI state) |
| `FutureProvider` | When you get data once (initial load) |

**Complete auth screen:**
```dart
class AuthScreen extends ConsumerWidget {
  const AuthScreen({super.key});

  @override
  Widget build(BuildContext context, WidgetRef ref) {
    return Scaffold(
      appBar: AppBar(title: Text('Sign In')),
      body: Padding(
        padding: EdgeInsets.all(24),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            TextField(
              decoration: InputDecoration(
                labelText: 'Email',
                prefixIcon: Icon(Icons.email),
              ),
              keyboardType: TextInputType.emailAddress,
              onChanged: (v) => ref.read(authFormProvider.notifier).setEmail(v),
            ),
            SizedBox(height: 16),
            TextField(
              decoration: InputDecoration(
                labelText: 'Password',
                prefixIcon: Icon(Icons.lock),
              ),
              obscureText: true,
              onChanged: (v) => ref.read(authFormProvider.notifier).setPassword(v),
            ),
            SizedBox(height: 24),
            ElevatedButton(
              onPressed: () => ref.read(authFormProvider.notifier).signIn(),
              child: Text('Sign In'),
            ),
            TextButton(
              onPressed: () => ref.read(authFormProvider.notifier).signUp(),
              child: Text('Create Account'),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### 25.4 Cloud Firestore — The Database

**What is Firestore?** A NoSQL database that stores data as **documents** inside **collections**.

```
Firestore Database
│
├── users (collection)
│   ├── user123 (document)
│   │   ├── name: "Alice"
│   │   ├── email: "alice@email.com"
│   │   └── age: 30
│   │
│   └── user456 (document)
│       ├── name: "Bob"
│       ├── email: "bob@email.com"
│       └── age: 25
│
└── todos (collection)
    ├── todo1 (document)
    │   ├── title: "Buy milk"
    │   ├── isDone: false
    │   └── userId: "user123"
    │
    └── todo2 (document)
        ├── title: "Study"
        ├── isDone: true
        └── userId: "user123"
```

**Setting up Firestore:**
```dart
import 'package:cloud_firestore/cloud_firestore.dart';

final FirebaseFirestore firestore = FirebaseFirestore.instance;
```

**CRUD with Firestore:**
```dart
class TodoFirestoreService {
  final CollectionReference _todos =
    FirebaseFirestore.instance.collection('todos');

  // CREATE — add a new document
  Future<void> addTodo(String title, String userId) async {
    await _todos.add({
      'title': title,
      'isDone': false,
      'userId': userId,
      'createdAt': FieldValue.serverTimestamp(),
      // FieldValue.serverTimestamp() = let server set the time
    });
  }

  // READ — get all todos for a user (once)
  Future<List<TodoModel>> getTodos(String userId) async {
    final snapshot = await _todos
      .where('userId', isEqualTo: userId)
      .orderBy('createdAt', descending: true)
      .get();

    return snapshot.docs.map((doc) {
      return TodoModel.fromFirestore(doc.id, doc.data() as Map<String, dynamic>);
    }).toList();
  }

  // READ — real-time listener (Stream)
  Stream<List<TodoModel>> streamTodos(String userId) {
    return _todos
      .where('userId', isEqualTo: userId)
      .orderBy('createdAt', descending: true)
      .snapshots()
      .map((snapshot) {
        return snapshot.docs.map((doc) {
          return TodoModel.fromFirestore(
            doc.id,
            doc.data() as Map<String, dynamic>,
          );
        }).toList();
      });
  }

  // UPDATE
  Future<void> toggleTodo(String docId) async {
    final todo = await _todos.doc(docId).get();
    final current = todo.data() as Map<String, dynamic>;
    await _todos.doc(docId).update({
      'isDone': !(current['isDone'] as bool),
    });
  }

  // DELETE
  Future<void> deleteTodo(String docId) async {
    await _todos.doc(docId).delete();
  }
}

// Model with Firestore conversion:
class TodoModel {
  final String? firestoreId;  // null = not yet saved to Firestore
  final String title;
  final bool isDone;
  final DateTime? createdAt;

  // From Firestore document
  factory TodoModel.fromFirestore(String id, Map<String, dynamic> data) {
    return TodoModel(
      firestoreId: id,
      title: data['title'] as String,
      isDone: data['isDone'] as bool? ?? false,
      createdAt: (data['createdAt'] as Timestamp?)?.toDate(),
    );
  }

  // To Firestore document
  Map<String, dynamic> toFirestore() => {
    'title': title,
    'isDone': isDone,
  };
}
```

**Firestore with Riverpod (StreamProvider):**
```dart
final todoStreamProvider = StreamProvider.family<List<TodoModel>, String>(
  (ref, userId) {
    return TodoFirestoreService().streamTodos(userId);
  },
);

// In widget:
final todosAsync = ref.watch(todoStreamProvider(currentUserId));
todosAsync.when(
  loading: () => CircularProgressIndicator(),
  error: (e, _) => Text('Error: $e'),
  data: (todos) => ListView.builder(
    itemCount: todos.length,
    itemBuilder: (ctx, i) => Text(todos[i].title),
  ),
);
```

#### 25.5 Firebase Storage — Images & Files

**What it does:** Lets users upload photos, documents, and other files.

```yaml
dependencies:
  firebase_storage: ^11.6.0
  image_picker: ^1.0.7      # Pick images from gallery/camera
```

**Upload and download:**
```dart
import 'package:firebase_storage/firebase_storage.dart';
import 'package:image_picker/image_picker.dart';

class StorageService {
  final FirebaseStorage _storage = FirebaseStorage.instance;

  // Pick image and upload
  Future<String> uploadProfileImage(String userId) async {
    // 1. Pick image from gallery
    final picker = ImagePicker();
    final XFile? image = await picker.pickImage(
      source: ImageSource.gallery,
      maxWidth: 1024,
      maxHeight: 1024,
    );

    if (image == null) throw Exception('No image selected');

    // 2. Create reference in Firebase Storage
    final ref = _storage.ref().child('profiles/$userId.jpg');

    // 3. Upload file
    await ref.putFile(File(image.path));

    // 4. Get download URL
    final downloadUrl = await ref.getDownloadURL();
    return downloadUrl;
  }

  // Delete a file
  Future<void> deleteImage(String path) async {
    await _storage.ref(path).delete();
  }
}
```

#### 25.6 Riverpod + Firebase — Complete Pattern

```dart
// 1. Auth provider (Stream from Firebase)
final authProvider = StreamProvider<User?>((ref) {
  return FirebaseAuth.instance.authStateChanges();
});

// 2. Current user ID (derived from auth)
final userIdProvider = Provider<String?>((ref) {
  return ref.watch(authProvider).valueOrNull?.uid;
});

// 3. Todo list provider (depends on userId)
final todoListProvider = StreamProvider<List<TodoModel>>((ref) {
  final userId = ref.watch(userIdProvider);
  if (userId == null) return Stream.value([]);
  return TodoFirestoreService().streamTodos(userId);
});

// 4. Todo actions
final todoActionsProvider = Provider<TodoFirestoreService>((ref) {
  return TodoFirestoreService();
});
```

**The full auth → data chain:**
```
Auth state changes → userIdProvider updates
  → todoListProvider reloads with new userId
    → Widgets rebuild with new data
```

#### 25.7 Firebase Security Rules (Important!)

Your database needs protection. By default, Firebase is open. **Fix this immediately.**

**Firestore rules (in Firebase Console → Firestore → Rules):**
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {

    // Only authenticated users can read/write their own data
    match /users/{userId} {
      allow read, write: if request.auth != null
        && request.auth.uid == userId;
    }

    match /todos/{document} {
      allow read, write: if request.auth != null
        && resource.data.userId == request.auth.uid;
    }
  }
}
```

**Storage rules:**
```
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /profiles/{userId} {
      allow read: if true;  // Anyone can view profile pics
      allow write: if request.auth != null
        && request.auth.uid == userId;
    }
  }
}
```

**Without security rules, anyone can delete your entire database. ALWAYS set rules.**

#### 25.8 Exercise: Add Firebase Auth to Todo App

Build a login screen that:
1. Lets users sign in with email/password
2. Shows the Todo list only when signed in
3. Shows a logout button in the AppBar
4. Persists the login session (Firebase handles this automatically)

```dart
// main.dart
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp();
  runApp(const ProviderScope(child: MyApp()));
}

// App router using auth state
class MyApp extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final authState = ref.watch(authProvider);

    return MaterialApp(
      home: authState.when(
        loading: () => Scaffold(body: Center(child: CircularProgressIndicator())),
        error: (e, _) => Scaffold(body: Center(child: Text('Error: $e'))),
        data: (user) => user != null ? TodoScreen() : LoginScreen(),
      ),
    );
  }
}
```

---

### Chapter 26: Supabase — Open-Source Firebase Alternative

#### 26.1 What is Supabase?

Supabase is an open-source alternative to Firebase. Instead of Google, it's built on:
- **PostgreSQL** — a powerful, traditional database (not NoSQL)
- **GoTrue** — authentication system
- **Realtime** — WebSocket-based live updates
- **Storage** — file storage (S3-compatible)

```
Firebase:   Google's closed-source, NoSQL (Firestore), limited queries
Supabase:   Open-source, PostgreSQL (full SQL), complex queries possible
```

**Analogy:** Firebase is like a modern apartment building (everything included, but you can't change the walls). Supabase is like a house you own (you have full control, but you need to do more yourself).

**When to use which:**
| Need | Better choice |
|------|---------------|
| Quick prototyping | Firebase |
| Complex queries (JOINs, aggregation) | Supabase |
| Full text search | Supabase |
| Real-time features | Both |
| Budget/Open-source requirement | Supabase |
| Google ecosystem integration | Firebase |
| Existing SQL knowledge | Supabase |

#### 26.2 Setting up Supabase

**Step 1: Create a Supabase project**
1. Go to [supabase.com](https://supabase.com) and sign up
2. Click "New project"
3. Enter name and database password
4. Choose a region close to your users
5. Wait for the database to provision (~2 minutes)

**Step 2: Get your API credentials**
In your Supabase project dashboard → Settings → API:
- **Project URL**: `https://xxxxxxx.supabase.co`
- **Anon public key**: `eyJhbGciOi...` (this is safe to include in your app)

**Step 3: Add Supabase to Flutter**
```yaml
dependencies:
  supabase_flutter: ^2.3.4
```

**Step 4: Initialize Supabase**
```dart
import 'package:flutter/material.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import 'package:supabase_flutter/supabase_flutter.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();

  await Supabase.initialize(
    url: 'https://xxxxxxx.supabase.co',
    anonKey: 'eyJhbGciOiJ...',
  );

  runApp(const ProviderScope(child: MyApp()));
}

// Access Supabase from anywhere in your app:
final supabase = Supabase.instance.client;
```

#### 26.3 PostgreSQL Basics

**What is PostgreSQL?** A relational database. Think of it as a collection of **tables** (like Excel sheets) that can reference each other.

```
Table: users                        Table: todos
┌─────────┬──────────┬──────┐       ┌─────────┬──────────┬──────────┬─────────┐
│ id (PK) │ email    │ name │       │ id (PK) │ title    │ is_done  │ user_id │
├─────────┼──────────┼──────┤       ├─────────┼──────────┼──────────┼─────────┤
│ uuid_1  │ a@b.com  │Alice │       │ todo_1  │Buy milk  │ false    │ uuid_1  │
│ uuid_2  │ c@d.com  │Bob   │       │ todo_2  │Study     │ true     │ uuid_1  │
└─────────┴──────────┴──────┘       └─────────┴──────────┴──────────┴─────────┘
                                          │                      │
                                          └────── FK ────────────┘
                                   (todos.user_id → users.id)
```

**Creating tables in Supabase:**
1. Go to Supabase Dashboard → SQL Editor
2. Run this SQL:

```sql
-- Create users table (Supabase creates this automatically via Auth)

-- Create todos table
CREATE TABLE todos (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  title TEXT NOT NULL,
  is_done BOOLEAN DEFAULT FALSE,
  user_id UUID REFERENCES auth.users(id) ON DELETE CASCADE
);

-- Allow users to read only their own todos
CREATE POLICY "Users can read own todos"
  ON todos FOR SELECT
  USING (auth.uid() = user_id);

-- Allow users to insert their own todos
CREATE POLICY "Users can insert own todos"
  ON todos FOR INSERT
  WITH CHECK (auth.uid() = user_id);
```

**Key PostgreSQL terms:**
| Term | Meaning | Example |
|------|---------|---------|
| `TABLE` | A collection of rows (like a sheet in Excel) | `todos` |
| `COLUMN` | A field in the table | `title`, `is_done` |
| `ROW` | One record | A single todo |
| `PRIMARY KEY (PK)` | Unique identifier for each row | `id` |
| `FOREIGN KEY (FK)` | Reference to another table | `user_id → users.id` |
| `UUID` | Universal Unique Identifier (safer than auto-increment) | `gen_random_uuid()` |
| `INDEX` | Speeds up searches | Created automatically on PKs |
| `POLICY` | Security rule (Row Level Security) | Users can only see their own data |

#### 26.4 Supabase Auth

**Sign up and sign in:**
```dart
class SupabaseAuthService {
  final supabase = Supabase.instance.client;

  // Sign up
  Future<AuthResponse> signUp(String email, String password) async {
    return await supabase.auth.signUp(
      email: email,
      password: password,
    );
  }

  // Sign in
  Future<AuthResponse> signIn(String email, String password) async {
    return await supabase.auth.signInWithPassword(
      email: email,
      password: password,
    );
  }

  // Sign out
  Future<void> signOut() async {
    await supabase.auth.signOut();
  }

  // Get current user
  User? get currentUser => supabase.auth.currentUser;

  // Listen to auth changes
  Stream<AuthState> get authState => supabase.auth.onAuthStateChange;
}
```

**Auth + Riverpod with Supabase:**
```dart
final supabaseAuthProvider = StreamProvider<User?>((ref) {
  final supabase = Supabase.instance.client;

  // Convert Supabase's AuthState stream to User? stream
  return supabase.auth.onAuthStateChange.map((event) {
    return event.session?.user;
  });
});
```

#### 26.5 Supabase Database — CRUD

```dart
class TodoSupabaseService {
  final supabase = Supabase.instance.client;

  // CREATE
  Future<void> addTodo(String title) async {
    final user = supabase.auth.currentUser;
    if (user == null) throw Exception('Not authenticated');

    await supabase.from('todos').insert({
      'title': title,
      'is_done': false,
      'user_id': user.id,
    });
  }

  // READ (once)
  Future<List<Map<String, dynamic>>> getTodos() async {
    final user = supabase.auth.currentUser;
    if (user == null) return [];

    final response = await supabase
      .from('todos')
      .select()
      .eq('user_id', user.id)
      .order('created_at', ascending: false);

    return response;
  }

  // READ (realtime via Stream)
  Stream<List<Map<String, dynamic>>> streamTodos() {
    final user = supabase.auth.currentUser;
    if (user == null) return Stream.value([]);

    return supabase
      .from('todos')
      .stream(primaryKey: ['id'])
      .eq('user_id', user.id)
      .order('created_at', ascending: false);
  }

  // UPDATE
  Future<void> toggleTodo(String id, bool currentValue) async {
    await supabase
      .from('todos')
      .update({'is_done': !currentValue})
      .eq('id', id);
  }

  // DELETE
  Future<void> deleteTodo(String id) async {
    await supabase
      .from('todos')
      .delete()
      .eq('id', id);
  }
}
```

**Supabase queries cheat sheet:**
```dart
// Select all
supabase.from('todos').select();

// Select specific columns
supabase.from('todos').select('id, title, is_done');

// Filter
supabase.from('todos').select().eq('is_done', true);
supabase.from('todos').select().neq('is_done', true);
supabase.from('todos').select().gt('created_at', someDate);
supabase.from('todos').select().lt('created_at', someDate);
supabase.from('todos').select().like('title', '%search%');

// Multiple conditions
supabase.from('todos').select()
  .eq('user_id', userId)
  .eq('is_done', false);

// Order
supabase.from('todos').select().order('created_at', ascending: false);

// Limit
supabase.from('todos').select().limit(10);

// Count
final count = await supabase.from('todos').count();

// Insert
supabase.from('todos').insert({'title': 'New', 'is_done': false});

// Update
supabase.from('todos').update({'is_done': true}).eq('id', todoId);

// Delete
supabase.from('todos').delete().eq('id', todoId);

// Raw SQL (for complex queries)
await supabase.rpc('my_custom_function', params: {'arg1': 'value'});
```

#### 26.6 Supabase Realtime

Supabase automatically supports real-time subscriptions. When any data changes in the database, your app gets notified instantly.

```dart
// Stream todos — updates automatically when DB changes
final todoStream = supabase
  .from('todos')
  .stream(primaryKey: ['id'])
  .eq('user_id', userId);

// Listen
todoStream.listen((List<Map<String, dynamic>> todos) {
  print('Todos updated: ${todos.length}');
});

// Widget:
class RealtimeTodoList extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final todosAsync = ref.watch(todoStreamProvider);

    return todosAsync.when(
      loading: () => CircularProgressIndicator(),
      data: (todos) => ListView.builder(
        itemCount: todos.length,
        itemBuilder: (ctx, i) => Text(todos[i]['title']),
      ),
      error: (e, _) => Text('Error: $e'),
    );
  }
}
```

**How it works:**
1. User A adds a todo → Supabase server updates the database
2. Server sends a notification to all connected clients
3. User B's app receives the change automatically
4. Riverpod's StreamProvider triggers a rebuild
5. User B sees the new todo without refreshing

**No polling, no manual refresh. It just works.**

#### 26.7 Supabase Storage

```dart
final supabase = Supabase.instance.client;

// Upload file
Future<String> uploadAvatar(String userId, XFile image) async {
  final bytes = await image.readAsBytes();
  final ext = image.name.split('.').last;

  final path = 'avatars/$userId.$ext';
  await supabase.storage.from('profiles').uploadBinary(path, bytes);

  // Get public URL
  final url = supabase.storage.from('profiles').getPublicUrl(path);
  return url;
}

// Download file
Future<List<int>> downloadFile(String path) async {
  final bytes = await supabase.storage.from('profiles').download(path);
  return bytes;
}

// Delete file
Future<void> deleteFile(String path) async {
  await supabase.storage.from('profiles').remove([path]);
}
```

#### 26.8 Supabase + Riverpod — Complete Example

```dart
// 1. Auth stream provider
final supabaseAuthProvider = StreamProvider<User?>((ref) {
  return Supabase.instance.client.auth.onAuthStateChange
    .map((event) => event.session?.user);
});

// 2. Current user provider
final currentUserProvider = Provider<User?>((ref) {
  return ref.watch(supabaseAuthProvider).valueOrNull;
});

// 3. Todo stream provider (depends on auth)
final supabaseTodosProvider = StreamProvider<List<Map<String, dynamic>>>((ref) {
  final user = ref.watch(currentUserProvider);
  if (user == null) return Stream.value([]);
  return TodoSupabaseService().streamTodos();
});

// 4. Widget
class TodoListWidget extends ConsumerWidget {
  @override
  Widget build(BuildContext context, WidgetRef ref) {
    final todosAsync = ref.watch(supabaseTodosProvider);

    return todosAsync.when(
      loading: () => const Center(child: CircularProgressIndicator()),
      error: (e, _) => Center(child: Text('Error: $e')),
      data: (todos) => ListView.builder(
        itemCount: todos.length,
        itemBuilder: (ctx, i) {
          final todo = todos[i];
          return ListTile(
            title: Text(todo['title']),
            trailing: Checkbox(
              value: todo['is_done'],
              onChanged: (_) => TodoSupabaseService().toggleTodo(
                todo['id'],
                todo['is_done'],
              ),
            ),
          );
        },
      ),
    );
  }
}
```

#### 26.9 Firebase vs Supabase — Which to choose?

| Factor | Firebase | Supabase |
|--------|----------|----------|
| **Database type** | NoSQL (documents) | SQL (PostgreSQL) |
| **Learning curve** | Easier (just read/write) | Steeper (need SQL basics) |
| **Queries** | Limited (no JOINs) | Full SQL power |
| **Real-time** | Built-in | Built-in |
| **Offline support** | Excellent | Limited |
| **Pricing** | Pay per read/write | Pay per database size |
| **Open source** | No | Yes |
| **Self-host** | No | Yes |
| **Ecosystem** | Huge (Google) | Growing |
| **Best for** | Quick apps, small data | Complex data, existing SQL |

**Decision flowchart:**
```
Do you know SQL? → Yes → Supabase
                → No  → Do you want to learn SQL?
                         → Yes → Supabase (great opportunity to learn)
                         → No  → Firebase

Is your data relational (users ↔ orders ↔ products)?
  → Yes → Supabase (JOINs make this easy)
  → No  → Either works

Need powerful offline support?
  → Yes → Firebase
  → No  → Either works
```

#### 26.10 Exercise: Migrate Todo App to Supabase

1. Set up a Supabase project
2. Create the `todos` table in SQL Editor
3. Set up Row Level Security policies
4. Replace the mock data provider with Supabase queries
5. Add email/password authentication
6. Test that data persists across app restarts

```dart
// Key files to modify:
// lib/providers/todo_provider.dart → use supabase instead of mock data
// lib/screens/todo_screen.dart → add auth state check
// lib/main.dart → initialize Supabase

// The rest of your UI (ListView, Checkbox, dialogs) stays the same!
// Only the data layer changes.
```

---

### Chapter 27: Common Patterns

```dart
class DataState<T> {
  final bool loading;
  final T? data;
  final String? error;

  const DataState({this.loading = false, this.data, this.error});

  DataState<T> copyWith({bool? loading, T? data, String? error}) =>
    DataState(loading: loading ?? this.loading, data: data ?? this.data, error: error ?? this.error);
}

// Usage in screen:
final state = ref.watch(dataProvider);
if (state.loading) return CircularProgressIndicator();
if (state.error != null) return Text('Error: ${state.error}');
return Text('Data: ${state.data}');
```

#### 27.2 Form validation

```dart
class FormState {
  final String email, password;
  final String? emailError, passwordError;
  final bool isLoading;

  const FormState({
    this.email = '', this.password = '',
    this.emailError, this.passwordError,
    this.isLoading = false,
  });

  FormState copyWith({...}) => ...;
}

// In notifier:
void setEmail(String v) {
  state = state.copyWith(
    email: v,
    emailError: v.isEmpty ? 'Email is required' :
                !v.contains('@') ? 'Invalid email' : null,
  );
}

// In screen:
TextField(
  onChanged: (v) => ref.read(formProvider.notifier).setEmail(v),
  decoration: InputDecoration(
    errorText: state.emailError,
  ),
)
```

#### 27.3 Search with debounce

```dart
// In notifier:
void setSearch(String query) {
  state = state.copyWith(search: query);
  _debounce?.cancel();
  _debounce = Timer(Duration(milliseconds: 300), () {
    // Perform actual search
    _performSearch(query);
  });
}
```

#### 27.4 Infinite scroll (pagination)

```dart
class PaginatedState {
  final List<Item> items;
  final bool loadingMore;
  final bool hasMore;
  final int page;

  const PaginatedState({
    this.items = const [],
    this.loadingMore = false,
    this.hasMore = true,
    this.page = 1,
  });

  PaginatedState copyWith({...}) => ...;
}

// In notifier:
Future<void> loadMore() async {
  if (state.loadingMore || !state.hasMore) return;
  state = state.copyWith(loadingMore: true);
  final newItems = await api.fetchPage(state.page + 1);
  state = state.copyWith(
    items: [...state.items, ...newItems],
    page: state.page + 1,
    loadingMore: false,
    hasMore: newItems.isNotEmpty,
  );
}

// In screen — detect scroll to bottom:
NotificationListener<ScrollNotification>(
  onNotification: (notification) {
    if (notification is ScrollEndNotification &&
        notification.metrics.pixels >= notification.metrics.maxScrollExtent - 200) {
      ref.read(provider.notifier).loadMore();
    }
    return false;
  },
  child: ListView.builder(
    itemCount: state.items.length + (state.loadingMore ? 1 : 0),
    // ...
  ),
)
```

#### 27.5 Dependent dropdowns

```dart
// Provider 1: Selected country
final countryProvider = NotifierProvider<CountryNotifier, String?>(...);

// Provider 2: Cities for selected country (derived)
final citiesProvider = Provider<List<String>>((ref) {
  final country = ref.watch(countryProvider);
  if (country == null) return [];
  return cityData[country] ?? [];
});
```

---

### Chapter 28: Testing

#### 28.1 Testing a Notifier

```dart
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import 'package:my_app/providers/todo_provider.dart';

void main() {
  group('TodoNotifier', () {
    test('initial state has 5 todos', () {
      final container = ProviderContainer();
      final state = container.read(todoProvider);
      expect(state.todos.length, 5);
      expect(state.filter, 'All');
      expect(state.search, '');
    });

    test('toggleTodo works', () {
      final container = ProviderContainer();
      container.read(todoProvider.notifier).toggleTodo(1);
      final todo = container.read(todoProvider).todos[0];
      expect(todo.isDone, true);
    });

    test('addTodo adds a todo', () {
      final container = ProviderContainer();
      container.read(todoProvider.notifier).addTodo('New task');
      expect(container.read(todoProvider).todos.length, 6);
    });

    test('deleteTodo removes a todo', () {
      final container = ProviderContainer();
      container.read(todoProvider.notifier).deleteTodo(1);
      expect(container.read(todoProvider).todos.length, 4);
    });

    test('setFilter updates filter', () {
      final container = ProviderContainer();
      container.read(todoProvider.notifier).setFilter('Done');
      expect(container.read(todoProvider).filter, 'Done');
    });

    test('filteredTodos returns correct items', () {
      final container = ProviderContainer();
      final notifier = container.read(todoProvider.notifier);

      expect(notifier.filteredTodos.length, 5); // 'All'

      notifier.setFilter('Done');
      expect(notifier.filteredTodos.length, 1); // Only id=3 is done

      notifier.setFilter('Pending');
      expect(notifier.filteredTodos.length, 4); // The rest
    });

    test('search filters correctly', () {
      final container = ProviderContainer();
      final notifier = container.read(todoProvider.notifier);

      notifier.setSearch('Riverpod');
      expect(notifier.filteredTodos.length, 1);
      expect(notifier.filteredTodos.first.title, 'Learn Riverpod');
    });
  });
}
```

#### 28.2 Testing a widget with providers

```dart
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';
import 'package:my_app/screens/todo_screen.dart';

void main() {
  testWidgets('TodoScreen shows todos', (tester) async {
    await tester.pumpWidget(
      const ProviderScope(child: MaterialApp(home: TodoScreen())),
    );

    // Should show 5 todos
    expect(find.text('Learn Dart basics'), findsOneWidget);
    expect(find.text('Build a Todo app'), findsOneWidget); // isDone=true

    // Toggle a todo
    await tester.tap(find.byType(Checkbox).first);
    await tester.pumpAndSettle();

    // Now the first todo should be done
    // The checkboxes should have updated
  });
}
```

#### 28.3 Run tests

```bash
flutter test                          # All tests
flutter test test/providers/          # Only provider tests
flutter test test/widgets/            # Only widget tests
flutter test --coverage               # With coverage report
```

---

### Chapter 29: Common Mistakes

#### 29.1 Top 10 mistakes beginners make

**Mistake 1: Forgetting `toList()` after `map()`**

```dart
// ❌ Returns lazy Iterable, not List
items.map((e) => e.copyWith(name: 'x'));

// ✅ Converts to List
items.map((e) => e.copyWith(name: 'x')).toList();
```

**Mistake 2: Using `ref.read` instead of `ref.watch` in build**

```dart
// ❌ Widget won't update
final count = ref.read(counterProvider);

// ✅ Widget subscribes to changes
final count = ref.watch(counterProvider);
```

**Mistake 3: Forgetting `.notifier`**

```dart
// ❌ Calling method on state
ref.read(counterProvider).increment();

// ✅ Calling method on notifier
ref.read(counterProvider.notifier).increment();
```

**Mistake 4: Mutating state directly**

```dart
// ❌ Same reference — no rebuild
void bad() {
  state.items[0].name = 'New';
  state = state;
}

// ✅ New reference — rebuilds
void good() {
  state = state.copyWith(
    items: state.items.map((e) {
      if (e.id == 1) return e.copyWith(name: 'New');
      return e;
    }).toList(),
  );
}
```

**Mistake 5: Creating providers inside build()**

```dart
// ❌ New provider every rebuild → infinite loop
@override
Widget build(BuildContext context) {
  final p = NotifierProvider<X, Y>(() => X());
}

// ✅ Provider at top level (outside any class)
final p = NotifierProvider<X, Y>(() => X());
```

**Mistake 6: Forgetting ProviderScope**

```dart
// ❌ Riverpod won't work
runApp(MyApp());

// ✅ Required
runApp(const ProviderScope(child: MyApp()));
```

**Mistake 7: Widget reading provider directly**

```dart
// ❌ Widget can't be reused
class MyCard extends ConsumerWidget {
  @override
  build(context, ref) {
    final data = ref.watch(specificProvider);
  }
}

// ✅ Widget receives data
class MyCard extends StatelessWidget {
  final Data data;
  const MyCard({required this.data});
}
```

**Mistake 8: Forgetting const constructor**

```dart
// ❌ Can't use `const MyWidget()`
class MyWidget extends StatelessWidget {
  MyWidget({super.key});
}

// ✅ Can use `const MyWidget()`
class MyWidget extends StatelessWidget {
  const MyWidget({super.key});
}

// Always use const when possible — performance!
```

**Mistake 9: Index out of bounds**

```dart
List items = [1, 2, 3];
print(items[3]);  // ❌ Error! Index 3 is out of bounds (0-2)

// Always check length first
if (index < items.length) print(items[index]);
```

**Mistake 10: Not handling null**

```dart
String? name;
print(name.length);  // ❌ Crash! name could be null

// Check first
if (name != null) print(name.length);

// Or use ?. and ??
print(name?.length ?? 0);
```

#### 29.2 Diagnostic checklist

When your app doesn't work as expected:

```
□ Log the error — check the debug console
□ Check ProviderScope in main.dart
□ Check ConsumerWidget (not StatelessWidget)
□ Check ref.watch (not ref.read) inside build()
□ Check ref.read (not ref.watch) in callbacks
□ Check .notifier when calling methods
□ Check state = state.copyWith(...) — not mutation
□ Check providers at top level (not inside build)
□ Check .toList() after .map() and .where()
□ Check const constructors
□ Check imports — correct paths?
□ Check null safety — ? and ?? used correctly?
□ Check pubspec.yaml — dependencies added?
□ Run flutter pub get
□ Run flutter clean
```

---

### Chapter 30: Next Steps

#### 30.1 What you've learned

By now you understand:
- **Dart**: variables, types, functions, classes, collections, null safety
- **Flutter**: widgets, layout, navigation, state, forms, lists
- **Riverpod**: providers, notifiers, state management, derived state
- **Architecture**: MVC pattern, separation of concerns, testing

#### 30.2 What to learn next

| Topic | Why | Resources |
|-------|-----|-----------|
| Async/Await | API calls, file I/O, timers | dart.dev/guides/language/language-tour |
| Streams | Real-time data, Firebase | dart.dev/tutorials/language/streams |
| Navigation 2.0 | Deep linking, web | docs.flutter.dev/ui/navigation |
| Animations | Beautiful UI | docs.flutter.dev/ui/animations |
| Firebase | Backend, auth, database | firebase.flutter.dev |
| StateNotifier | Legacy but still used | pub.dev/packages/flutter_riverpod |
| Code generation | json_serializable, freezed | pub.dev/packages/json_serializable |
| BLoC | Alternative to Riverpod | flutter.dev/bloc |

#### 30.3 Practice projects

Build these in order:

1. **Counter app** — Simple, teaches state management basics
2. **Todo app** — CRUD operations, filtering, search
3. **Weather app** — API calls, async state, location
4. **Shopping cart** — Multiple screens, shared state, totals
5. **Social feed** — Infinite scroll, likes, comments
6. **Chat app** — Real-time messages, Firebase

#### 30.4 Final advice

1. **Build something every day.** Even 30 minutes of coding beats 5 hours of reading.
2. **Read error messages.** Flutter/Dart error messages are usually very clear about what's wrong.
3. **Use the debugger.** `print()` is your friend. So is `debugger` statement.
4. **Ask questions.** Stack Overflow, Flutter Discord, Reddit r/FlutterDev.
5. **Study other people's code.** GitHub has thousands of Flutter projects.
6. **Don't copy-paste without understanding.** Type it out yourself.
7. **Start simple.** A working simple app is better than a broken complex one.
8. **It's OK to not know.** Every expert was once a beginner.

---

## Glossary

| Term | Definition |
|------|-----------|
| **AnimatedContainer** | Widget that automatically animates property changes (color, size, etc.) |
| **Animation curve** | Defines acceleration/deceleration of an animation (`easeIn`, `bounceOut`) |
| **API** | Application Programming Interface — how apps talk to servers |
| **Arrow function** | `int add(a, b) => a + b` — shorthand for one-line functions |
| **async/await** | Pattern for writing asynchronous code that looks synchronous |
| **bool** | Type that can be `true` or `false` |
| **BuildContext** | A widget's location in the widget tree, used for theme/navigation access |
| **debugPrint()** | Function for logging during development (won't be truncated) |
| **Future** | A value that will be available later (result of async operation) |
| **FutureBuilder** | Flutter widget that builds UI based on Future state (loading/data/error) |
| **GoRouter** | Recommended routing package for Flutter with path parameters and deep linking |
| **Hero** | Widget that creates a shared-element transition between two screens |
| **Class** | Blueprint for creating objects |
| **Comment** | Text in code ignored by the computer (`//` or `/* */`) |
| **const** | Compile-time constant — value known before the app runs |
| **Constructor** | Special method that creates an instance of a class |
| **ConsumerWidget** | A StatelessWidget that can read providers via `ref` |
| **copyWith** | Method that creates a new object with some fields changed |
| **Dart** | Programming language used to write Flutter apps |
| **Database** | Structured collection of data stored on disk (SQLite, Firestore, PostgreSQL) |
| **double** | Type for decimal numbers (e.g., 3.14) |
| **File I/O** | Reading and writing files on the device (images, documents, JSON) |
| **Firebase** | Google's backend platform (Auth, Firestore, Storage, Notifications) |
| **Firestore** | Firebase's NoSQL database — stores data as documents in collections |
| **Firebase Auth** | Firebase service for user sign-in (email, Google, Apple, phone) |
| **Enum** | A fixed set of named values (e.g., `Day.monday`) |
| **final** | Variable that can only be assigned once (at runtime) |
| **Flutter** | UI framework for building apps with Dart |
| **Function** | A named block of reusable code |
| **Getter** | Computed property that acts like a field (`get area => w * h`) |
| **Immutability** | Objects that can't be changed after creation |
| **int** | Type for whole numbers (e.g., 42) |
| **JSON** | Data format for exchanging information between apps and servers |
| **List** | Ordered collection of items (`[1, 2, 3]`) |
| **Map** | Key-value collection (`{'name': 'Alice'}`) |
| **Model** | Pure Dart class describing data shape |
| **MVC** | Model-View-Controller — code organization pattern |
| **Navigator** | Flutter widget that manages a stack of screens (push/pop) |
| **Notifier** | Riverpod class that manages mutable state |
| **NotifierProvider** | Riverpod provider using a Notifier for mutable state |
| **Null safety** | Dart feature preventing null reference errors |
| **NoSQL** | Database type that stores data as documents (Firestore) instead of tables |
| **PostgreSQL** | Powerful SQL database used by Supabase (tables, JOINs, indexes) |
| **Persistence** | Data that survives app restarts (saved to device storage) |
| **Row Level Security** | Database security that restricts data access per user |
| **SharedPreferences** | Simple key-value storage for small data (settings, preferences) |
| **SQLite** | Lightweight SQL database that lives in a single file on the device |
| **Supabase** | Open-source Firebase alternative (PostgreSQL + Auth + Realtime + Storage) |
| **StreamProvider** | Riverpod provider that subscribes to a Stream (auth state, realtime data) |
| **Parameter** | Input to a function (`int add(int a, int b)`) |
| **Provider** | Riverpod object holding and distributing state |
| **ProviderScope** | Required widget wrapping the app for Riverpod |
| **ref** | Object for interacting with providers (watch, read) |
| **ref.read()** | Get provider value once (no subscription) |
| **ref.watch()** | Subscribe to provider (rebuild on changes) |
| **required** | Parameter must be provided |
| **Riverpod** | State management library for Flutter |
| **setState()** | Flutter method triggering widget rebuild |
| **Spread operator** | `...` — expands a collection into another |
| **Status code** | HTTP response status (200=OK, 404=Not Found, 500=Server Error) |
| **Stream** | Multiple values delivered over time (like a Future but for many values) |
| **StreamBuilder** | Flutter widget that builds UI based on Stream state |
| **StatefulWidget** | Widget that can change via `setState()` |
| **StatelessWidget** | Widget that never changes |
| **String** | Type for text (`'Hello'`) |
| **var** | Type inference — Dart determines the type |
| **Widget** | Everything on screen in Flutter |
| **WidgetRef** | The `ref` object in ConsumerWidget.build() |
