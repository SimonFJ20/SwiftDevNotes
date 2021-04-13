
# Swift programming language

- [Swift programming language](#swift-programming-language)
  * [Basics](#basics)
    + [Types](#types)
    + [Variables](#variables)
    + [Arrays](#arrays)
    + [Dictionaries](#dictionaries)
    + [Null type](#null-type)
    + [Functions](#functions)
    + [Switch Statements](#switch-statements)
    + [For loops](#for-loops)
    + [Do-While loop](#do-while-loop)
    + [Classes](#classes)
    + [STD Lib](#std-lib)
  * [UIKit](#uikit)
    + [Boilerplate](#boilerplate)
  * [SwiftUI](#swiftui)
    + [Boilerplate](#boilerplate-1)

## Basics

Swift is a type safe and type inferred language, with implicit type declaration.

- Type safe: Keeps track of variable types, and the option to declare types explicitly `let name: Integer`
- Type inferred: Throws errors at type mismatches
- Implicit type declaration: You dont have to declare type explicitly `let name = 0`

Swift writing dynamics is like JS: 
- `;` are optional
- Whitespace is prefference based, meaning code does not depend on it, except strings
- Implicit types like js, allthough inferred
- Syntax is javalike, like JS 

### Types

All types in swift are 64 bits (expept strings), for performance reasons

```swift
T = Type
let name: Int = 123; // 16 bits/2 bytes in principle
let name: Float = 1.13; // 32 bits/4 bytes in principle
let name: Double = 1.23; // 64 bits/8 bytes in principle
let name: String = "text"; // 8 bits/1 byte per char depends on the length in princliple
let name: Bool = false; // 1 bit in principle
```

### Variables

```swift
// js-const
let name: T;
let name = 0;

// js-let
var name: T;
var name = 0;
```

### Arrays

```swift
let myArr: [Int] = [];
let myArr = [Int]();
myArr = [0, 5, 2, 5, 6, 3];
myArr[index];
myArr.insert(value, at: Int);
myArr.remove(at: Int); // also shifts array
myArr.append(value);
myArr.index(value); // search
myArr += [value, value];
```

### Dictionaries

```swift
let myDict: [String: Int] = [];
let myDict = [String: Int]();
myDict = ["one": 1, "two" 2: "three": 3];
myDict["one"] == 1;
myDict["four"]; // error
myDict["four"] = 4;
myDict["four"]; // no error


```

### Null type

```swift
let name: Type? = nil;
if(name != nil) {
    // do code
}
if(let name = SomethingThatCanBeNil()) {
    varThatMustNotBeNil = nil;
}
// if nil, then error is thrown
let name: SomethingThatCanBeNil! = SomethingThatCanBeNil();
```

### Functions

```swift
// js-const name = () => {}
func name() {
    // code
}
name();

func name(par1: T, arg2 par2: T, _ par3: t) -> T {
    return parameter;
}
let t1 = new T();
let t2 = new T();
let t3 = new T();
let name: T = name(par1: t1, arg2: t2, t);
```

### Switch Statements

Switch statements break automatically.

```swift
switch(arg: T) {
    case yourCase1:
        // code
        // no break;
    case yourCase2, yourCase3:
        // code
        // no break;
    default:
        // code
}
```

### For loops

```swift
for(i in lower: Int...upper: Int) {
    // your code
}
for(item in myArr) {
    doSometingWith(item);
}
for((key, value) in dict) {
    doSometingWith(key, value);
}
```

### Do-While loop

```swift
repeat {

} while(true)
```

### Classes

```swift
class MyClass {
    var prop1: T;
    var prop2 = T();
    init() {
        // constructor
        self.prop1 = T();
    }
    func propFunc() {
        // code
    }
}

class MyInheritedClass {
    var prop3: T;
    var prop3: Int {
        // compute value
        return 1;
    }
    overrride init() {
        super.init();
    }
    convenience init(_ p3: T) {
        self.init();
        self.prop3 = p3;
    }
    override func propFunc() {
        super.propFunc();
    }
    func propFunc2() {
        // code
    }
}

let myClass = MyClass();
MyClass().prop1 = T();
MyClass().propFunc();

let myInClass = MyInheritedClass();
let nt = T();
let myInClass2 = MyInheritedClass(nt);

```

### STD Lib
```swift
// js-console.log()
print(string: String);
let name: T;
print("something \(name) something");
```

## UIKit

For All IOS, may be deprecated in the future.

### Boilerplate

```swift
import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad();

        // your code here

        // Create label
        let label = UILabel();
        label.text = "UIKit works!";
        label.translatesAutoresizingMaskIntoConstraints = false;
        view.addSubview(label);

        // Create center constraints
        let centerX = NSLayoutConstraint(
            item: label, 
            attribute: .centerX, 
            relatedBy: .equal, 
            toItem: view, 
            attribute: .centerX, 
            multiplier1: 1, 
            constant: 0
        );
        let centerY = NSLayoutConstraint(
            item: label, 
            attribute: .centerY, 
            relatedBy: .equal, 
            toItem: view, 
            attribute: .centerY, 
            multiplier1: 1, 
            constant: 0
        );

        // Add constraints to parent
        view.addConstraint([centerX, centerY]);

    }

}
```

## SwiftUI

Really new, but Apple says this is the future for IOS
Only runs on IOS 13+

### Boilerplate

```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        Text("SwiftUI is working!");
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView();
    }
}
```

