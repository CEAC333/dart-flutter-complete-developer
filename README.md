# dart-flutter-complete-developer

## Let's Dive In!

  ### How to Get Help
  
  ### Course Organization
  
  Dart (Programming Language) + Flutter (Mobile UI Framework) = Usable App
  
  **Course Flow**
  
  - Basics of the Dart Language (Browser-based Editor)
  
  - Building Projects + Packages with Dart (Local Code Editor)
  
  - Building Apps with Dart + Flutter (Local Code Editor + Mobile Device Emulator)

## A Dart Introduction

  ### Dart Overview
  
  **Few Notes on Dart**
  
  - Object-Oriented Language - (*Most of our time is spent thinking about how to organize code in objects, or 'classes'*)
  
  - Statically Typed - (*Variables contain data of a single 'type', like an integer or a string*)
  
  - C-style Syntax - (*Syntax of the language is very similar to C, C#, Javascript*)
  
  - Multiple Runtime Environments - (*Transpiled to Javascript to run in the browser. Runs in the 'Dart VM' to execute from a command line. Compiled to machine code to run on mobile devices*)
  
  ### The Dartpad Editor
  
  - https://dartpad.dartlang.org/ - Browser based tool for *playing around* with Dart
  
  ### Our First Program
  
```dart
void main() 
{
  var name = myName();
  
  print('My name is $name');
}

String myName() 
{
  return 'Stephen';
}
```

### Pulling the Pieces Apart

```
var name = myName();
```

var - *Declares a variable*

name - *Variable's name is 'name'*

var name - *Variable Declaration*

myName(); - *Runs the 'myName' function*

= myName(); - *Variable Initialization*

### Functions in Dart

```dart
String myName() 
{
  return 'Stephen';
}
```

String - *Type of value that will be returned*
myName - *Name of Function*
() - *Argument List*
return 'Stephen'; - *Function Body*

**Time**

- Program starts up

- Dart finds and runs the 'main' function

- Main function starts up the rest of our app

### Introduction to Types

**Types in Dart**

- Every value has a 'type'

- Every variable has a type it can reference

- Once a variable has a 'type' associated, the variables type cannot change

- We don't always have to annotate types, Dart can guess for us

**Your Computers Memory**

```dart
name -> 'Stephen'
```

name - *Variable that can reference type String*
'Stephen' - *Value with type String*

TYPE ERROR EXAMPLE:

```dart
void main() 
{
  var name = myName();
  
  name = 123;
  
  print('My name is $name');
}

String myName() 
{
  return 'Stephen';
}
```

`A value of type 'int' can't be assigned to a variable of type 'String'`

```dart
name -> 'Stephen'
```

name - *Variable that can reference type String*
'Stephen' - *Value with type String*

TYPE INFERENCE EXAMPLE:

```dart
void main() 
{
  var name = myName();
  
  print('My name is $name');
}

myName() 
{
  return 'Stephen';
}
```

### Why Use Types?

| Type | Example Value |
|---|---|
| String | 'hi', 'Hows it going?', 'Thats great' |
| int  | 0, -999, 876000   |
| double  | 0.0001, -999.814, 100.1 |
| dynamic  | 'Hi', -0.0004, 90  |

TYPE ERROR EXAMPLE:

```dart
void main() 
{
  var name = myName();
  name.length;
  print('My name is $name');
}

int myName() 
{
  return 123;
}
```

`The getter 'length' isn't defined for the class 'int'`

**Why types at all?**

- Performance can be improved

- Easier to work on large projects

- Less of a need to write unit tests

- Automatically find simple errors

### String Interpolation

```dart
void main() 
{
  var name = myName();

  print('My name is ${name.length}');
}

myName() 
{
  return 'Stephen';
}
```

`My name is Stephen.length`

```dart
void main() 
{
  var name = myName();

  print('My name is $name.length');
}

myName() 
{
  return 'Stephen';
}
```

`My name is 7`

### Object Oriented Programming in Dart

- Object (Pieces of Data <- Methods)

Piece of Data - *Information about our application hidden from other parts of the app*

Method - *Functions that govern access to data stored in the object*

- Class (Pieces of Data <- Methods) - Template of the Objects

- Object/Instance ('red', 123 <- Methods)

Class (House Blueprints) -> Instances (Each Instance is a House)

### Creating Classes

#### Person Class

| Fields | |
|---|---|
| name | type |
| firstName | string |

| Methods |
|---|
| name | 
| printName | 

```dart
class Person
{
  String firstName;
  
  printName() 
  {
    print(firstName);
  }
}
```

### Creating Class Instances

```dart
void main()
{
  var person = new Person();
  
  person.firstName = 'Stephen';
  
  person.printName();
}

class Person
{
  String firstName;
  
  printName() 
  {
    print(firstName);
  }
}
```

### Constructor Functions

```dart
void main()
{
  var person = new Person('Stephen');
  
  person.printName();
}

class Person
{
  String firstName;
  
  Person(this.firstName);
  
  printName() 
  {
    print(firstName);
  }
}
```

**Time**

- Call classes constructor function with arguments

- Constructor function executed, does some initial setup

- New instance of class returned

### Review on Constructors

```dart
class Person
{
  String firstName;
  
  Person(this.firstName);
}
```

Person - *Constructor function because it has the same name as the class*

```dart
new Person('Stephen');
```

'Stephen' - *First argument to constructor function*

### Completed Code

- https://github.com/StephenGrider/FlutterCasts/

## Staying on Target with Dart

### App Overview

**Deck of Cards**

- Ace of Diamonds

- Two of Diamonds

- Three of Diamonds

- Four of Diamonds

- Ace of Spades

**Deck Program**

- Make a Deck - *Create a new deck of playing cards*

- printCards - *Print all the cards in this deck*

- shuffle - *Shuffle the cards in this deck*

- cardsWithSuit - *Find all the cards with a given suit*

- deal - *Deal out some number of cards from this deck*

- removeCard - *Remove a specific card from the deck*

### OOP Design Flow

**Dart Program Design Flow**

| Think about... |   | Then...  |  
|---|---|---|
| What different *types* of 'things' exist in our app? | -> | Create a dart 'class' to represent each type of 'thing' |
| What pieces of data would be tied to each 'thing'? | -> | Create a 'field' on each class to hold that piece of data | 
| How would we interact with each 'thing' and the data it contains? | -> | Add methods to represent each interaction | 
| How do different 'things' interact with each other? | -> | Write code outside of a class to get classes to interact | 

#### Deck Class

| Fields | |
|---|---|
| name | type |

| Methods |
|---|
| name | 

#### Card Class

| Fields | |
|---|---|
| name | type |

| Methods |
|---|
| name | 

```dart
class Deck
{

}

class Card
{

}
```

### Adding Fields to Classes

#### Deck Class

| Fields | |
|---|---|
| name | type |
| cards | List<Card> |

| Methods |
|---|
| name |  

#### Card Class

| Fields | |
|---|---|
| name | type |
| suit | string |
| rank | string |

| Methods |
|---|
| name | 

```dart
class Deck
{
  List<Card> cards;
}

class Card
{
  String suit;
  String rank;
}
```

### Associated Methods

#### Deck Class

| Fields | |
|---|---|
| name | type |
| cards | List<Card> |

| Methods |
|---|
| name | 
| printCards | 
| shuffle | 
| deal | 
| removeCard | 

#### Card Class

| Fields | |
|---|---|
| name | type |
| suit | string |
| rank | string |

| Methods |
|---|
| name | 
| ??? | 

### More Initialization with Constructors

```dart
class Deck
{
  List<Card> cards;
  
  Deck()
  {
    
  }
}

class Card
{
  String suit;
  String rank;
}
```

### For Loops

- ranks = ['Ace', 'Two', 'Three', 'Four', ...]

- suit = ['Hearts', 'Diamonds', ...]

For every suit in the suits list ...

  * For every rank in the ranks list ...
  
    * Create a new card and add it to the 'cards' list

```dart
class Deck
{
  List<Card> cards;
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        
      }
    }
  }
}

class Card
{
  String suit;
  String rank;
}
```

### Adding Elements to Lists

```dart
void main()
{
  new Deck();
}

class Deck
{
  List<Card> cards;
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
}
```

`Uncaught exception: C.JSNull_methods.add$1 is not a function`

### More on Variable Initialization

```dart
List<Card> cards
```

List<Card> - *Declares a field*
  
cards - *Fields name is 'cards'*

List<Card> cards - *Variable declaration*
  
**Your Computers Memory**

cards -> ???

cards (Variable that can reference type List<Card>)
  
cards -> null

```dart
void main()
{
  new Deck();
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
}
```

### Customizing Print Statements

```dart
void main()
{
  var deck = new Deck();
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
}
```

`Instance of 'Deck'`

```
print ( value )
```

value - *Do you have a 'toString()' method? If so, run it!*

```dart
void main()
{
  var deck = new Deck();
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return 'This is a deck!';
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
}
```

### ToString on Cards

```dart
void main()
{
  var deck = new Deck();
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Shuffling a List

- Dart Documentation - https://api.dartlang.org/stable/2.0.0/index.html

- List Class Docs - https://api.dartlang.org/stable/2.0.0/dart-core/List-class.html

- Look for the method `shuffle`

```dart
void main()
{
  var deck = new Deck();
  deck.shuffle();
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Annotating Argument Types

**Deck of Cards**

- Ace of Diamonds

- Two of Diamonds

- Three of Diamonds

- Aces of Spades

- Two of Spades

--------> cardsWithSuit('Spades') -------->

- Ace of Spades

- Two of Spades

```dart
void main()
{
  var deck = new Deck();
  deck.shuffle();
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit)
  {
    
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Filtering Lists

```dart
void main()
{
  var deck = new Deck();
  deck.shuffle();
  print(deck.cardsWithSuit('Diamonds'));
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit)
  {
    return cards.where((card) 
    {
      return card.suit == suit;
    });
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Annotating Argument Types

```dart
void main()
{
  var deck = new Deck();
  deck.shuffle();
  print(deck.cardsWithSuit('Diamonds'));
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit)
  {
    return cards.where((card) => card.suit == suit);
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Filtering Lists

- List Class Docs - https://api.dartlang.org/stable/2.0.0/dart-core/List-class.html

- Look for the method `sublist`

**Cards**

- Card 0
- Card 1
- Card 2
- Card 3
- Card 4
- Card 5

**Memory**

List:

- 0 -> Card # 1 
- 1 -> Card # 2 
- 2 -> Card # 3 
- 3 -> Card # 4 

SubList:

- 0 -> Card # 1 
- 1 -> Card # 2 

### Shorthand Function Syntax

```dart
void main()
{
  var deck = new Deck();
  
  print(deck);
  print(deck.deal(5));
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit)
  {
    return cards.where((card) => card.suit == suit);
  }
  
  deal(int handSize)
  {
    var hand = cards.sublist(0, handSize);
    cards = cards.sublist(handSize);
    
    return hand;
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Removing Individual Records

- https://api.dartlang.org/stable/2.0.0/dart-core/List-class.html

- Method `removeWhere`

### RemoveCard Implementation

```dart
void main()
{
  var deck = new Deck();
  
  deck.removeCard('Diamonds', 'Ace');
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var suit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(rank, suit);
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit)
  {
    return cards.where((card) => card.suit == suit);
  }
  
  deal(int handSize)
  {
    var hand = cards.sublist(0, handSize);
    cards = cards.sublist(handSize);
    
    return hand;
  }
  
  removeCars(String suit, String rank)
  {
    cards.removeWhere((card) => (card.suit == suit) && (card.rank == rank));
  }
}

class Card
{
  String rank;
  String suit;
  
  Card(this.rank, this.suit);
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

### Named Parameters

```dart
void main()
{
  var deck = new Deck();
  
  deck.removeCard('Diamonds', 'Ace');
  print(deck);
}

class Deck
{
  List<Card> cards = [];
  
  Deck()
  {
    var ranks = ['Ace', 'Two', 'Three', 'Four', 'Five'];
    var suits = ['Diamonds', 'Hearts', 'Clubs', 'Spades'];
    
    for(var mySuit in suits)
    {
      for(var rank in ranks)
      {
        var card = new Card(
          suit: mySuit, 
          rank: rank
        );
        cards.add(card);
      }
    }
  }
  
  toString()
  {
    return cards.toString();
  }
  
  shuffle()
  {
    cards.shuffle();
  }
  
  cardsWithSuit(String suit)
  {
    return cards.where((card) => card.suit == suit);
  }
  
  deal(int handSize)
  {
    var hand = cards.sublist(0, handSize);
    cards = cards.sublist(handSize);
    
    return hand;
  }
  
  removeCars(String suit, String rank)
  {
    cards.removeWhere((card) => (card.suit == suit) && (card.rank == rank));
  }
}

class Card
{
  String rank;
  String suit;
  
  Card({this.rank, this.suit});
  
  toString()
  {
    return '$rank of $suit';
  }
}
```

## Flutter Environment Setup - MacOS

  ### Flutter Setup on MacOS
  
  ### SDK Extraction
  
  ### Editing the PATH Variable
  
  ### XCODE License
  
  ### Generating Flutter Projects
  
## MacOS Setup - Android

  ### Android Setup on MacOS
  
  ### Android Dependencies
  
  ### Android Project Setup
  
  ### More Android Dependencies!
  
  ### Android Emulator Creation
  
  ### Flutter Startup
  
  ### Finished Android Setup

## MacOS Setup - iOS

  ### iOS on Mac Setup
  
  ### XCode Setup
  
  ### iOS Simulator Startup
  
  ### App Startup

## Flutter Setup on PC

### Flutter Install

- https://flutter.io/docs/get-started/install/windows

### More Flutter Installation

### Android Install

### Additional Dependencies

### Generating a Project

- Start New Android Studio Project -> Next -> Next -> Next -> Next

### Selecting an Image

- AVD Manager -> Create Virtual Device

### Starting the Emulator

### Finishing Android Setup

```
flutter emulators
```

```
flutter run
```

## App Building Time!

### Code Editor Setup

- https://code.visualstudio.com/download

**1. Download VS Code**

In your browser, navigate to https://code.visualstudio.com/download and download the version of VS Code appropriate for your operating system.

**2. Install VS Code**

Once you've downloaded the installer, run it to start up the VS Code installer.

**3. Start VS Code**

**4. Install the Flutter editor package**

With VS Code open, find the menu bar at the top marked 'View' then click on 'Extensions'.  This will open up a side bar tab used to install extensions.  Search for a package called 'Flutter' and click the green 'install' button. 

### What's Flutter About, Anyways?

### App Overview

### The Four Step Design Process

### Import Statements

### Creating Widgets

### Displaying Content on Screen

### Showing a Scaffold

### Customizing the App Bar

### Named Parameter Clarification

### Required Parameters

### Child Parameters

### Displaying Icons

### Adding Custom Widgets

## State Design with Flutter Apps

  ### Stateless vs Stateful Widgets
  
  ### The Build Method
  
  ### Local Import Statements
  
  ### Quick Breather and Review
  
  ### Refactoring Stateless to Stateful
  
  ### More Refactoring to Stateful Widgets

## High-Level Dart

  ### Generics in Dart
  
  ### Why Two Classes?

## HTTP Requests with Flutter

  ### Photos API
  
  ### Working with JSON
  
  ### Casting JSON to Model Instances
  
  ### Named Constructors
  
  ### Adding an Image Model
  
  ### Function References
  
  ### The HTTP Package
  
  ### Issuing HTTP Requests
  
  ### Handling Dart Futures
  
  ### Parsing Future Responses into a Model
  
  ### Updating the AppState Widget
  
  ### Building Lists of Widgets
  
  ### Sending Images to the ImageList
  
  ### The Final Keyword
  
  ### Building List of Widgets
  
  ### Sending Images to the ImageList
  
  ### The Final Keyword
  
  ### Building Lists with ListView
  
  ### Listing URL's
  
  ### Text to Images
  
  ### Containers for Positioning
  
  ### Adding Border Style
  
  ### Column Widgets for Layout
  
  ### Selective Padding
  
  ### App Review

## Forms and Validation with Flutter

  ### App Overview
  
  ### Boilerplate App Code
  
  ### Creating the Login Screen
  
  ### More Container Styling
  
  ### Labels and Hint Text
  
  ### Customizing Keyboard Type
  
  ### Handling Password Inputs
  
  ### Displaying Buttons with RaisedButton
  
  ### Changing Widgets Colors
  
  ### Layout Control
  
  ### Form Validation
  
  ### Referencing Widgets with Global Keys
  
  ### The Form Widget and Form State
  
  ### Creating a Global Key
  
  ### Referencing FormState with Global Keys
  
  ### Validating via FormState
  
  ### Triggering Validation
  
  ### Retrieving Form Values
  
  ### Final Form Submittal
  
  ### Code Reuse with Mixins
  
  ### Mixin Validator Implementation

## Reactive Programming with Dart

  ### A Quick Detour
  
  ### Streams by Analogy
  
  ### Characteristics of Streams
  
  ### StreamControllers and Sinks
  
  ### Mapping a Stream
  
  ### Adding a StreamTransformer
  
  ### Implementing the Listener
  
  ### Stream Review
  
  ### Let's Build a Game
  
  ### Why Streams?
  
  ### Word Guessing
  
  ### Stream's 'Take' and 'Where' Functions
  
  ### Validation with Streams
  
  ### Email Validation
  
  ### Wiring up the Error

## Advanced Flutter Architecture - The Bloc Pattern

  ### BLOC's vs Stateful Widgets
  
  ### The Purpose of Streams with Blocs
  
  ### Generating a New Project
  
  ### App Boilerplate
  
  ### Second Time on LoginScreen
  
  ### TextFields with RaisedButtons
  
  ### How to Use TextFields
  
  ### BLOC Design for TextFields
  
  ### Annotating Stream Types
  
  ### Issues with Bloc Access
  
  ### Shortcut Access with Getters
  
  ### Public vs Private Fields
  
  ### Improving the BLOC Api
  
  ### Validation Transformers
  
  ### A Technicality Around Mixins
  
  ### Cleaning Up Controllers
  
  ### Bloc Application

## Consuming BLOC Data

  ### The StreamBuilder Widget
  
  ### Streambuilder for Password Fields
  
  ### Scoped Bloc Approach
  
  ### Provider Implementation
  
  ### The Provider Implementation
  
  ### The Provider's 'of' Function
  
  ### The Provider's Constructor
  
  ### The Provider in Action
  
  ### Accesing the Bloc
  
  ### Breather and Review
  
  ### Enabling Form Submission
  
  ### Stream Merging Possibilities

## RxDart for Reactive Programming

  ### Introducing RxDart
  
  ### More on RxDart
  
  ### The CombineLastest Function
  
  ### CombineLatest in Action
  
  ### More on StreamBuilder
  
  ### Interpreting Stream Values
  
  ### Broadcast Streams
  
  ### Disabled by Default
  
  ### Replacing Controllers with Subjects
  
  ### Review of BLOCs

## Building Delightful Animations

  ### App Overview
  
  ### Animation Library Classes
  
  ### App Boilerplate
  
  ### StatefulWidgets for Animations
  
  ### Widget Structure
  
  ### Displaying a Cat
  
  ### The InitState Method
  
  ### Declaring the TickerProvider
  
  ### Tweens with Curves
  
  ### Performance Savings with AnimatedBuilder
  
  ### Nature of Animation
  
  ### Starting the Animation
  
  ### Watching for Taps with GestureDetector
  
  ### Reversing Animation States
  
  ### Building the Box
  
  ### Layouts with the Stack Widget
  
  ### Order of Drawing Widgets
  
  ### Add Center Widget
  
  ### Positioned Widgets
  
  ### Expanding Stack Dimensions
  
  ### Three Reasons for Strange Layouts
  
  ### Positioned Constrains
  
  ### Negative Offsets
  
  ### Stack Clip Settings
  
  ### Adjusting Tween Ranges
  
  ### Adding Box Flaps
  
  ### Rotating Widgets
  
  ### Rotation by Radians
  
  ### Changing Rotation Point
  
  ### A Touch of Positioning
  
  ### BoxAnimation Controller
  
  ### Adding Animated Builders
  
  ### Resetting Animations
  
  ### Constraining Animation Range
  
  ### Adding the Right Flap
  
  ### Negative Rotation Values
  
  ### Toggling Animation State
  
  ### Animation Wrapup

## Performant Data Fetching

  ### App Overview
  
  ### Hacker News API
  
  ### More API Challenges
  
  ### API Peformance Strategy
  
  ### Creating the ItemModel Class
  
  ### A Few More ItemModel Properties
  
  ### API Provider Implementation
  
  ### Fetching Individual Items

## Testing with Flutter and Dart

  ### Testing with Dart
  
  ### A Few Imports
  
  ### Writing Expectations
  
  ### Mocking HTTP Requests
  
  ### Returning JSON
  
  ### Testing FetchItem

## Offline Data Storage

  ### SQLite DB Provider
  
  ### Database Imports
  
  ### Async Constructors
  
  ### Creating a DB Connection
  
  ### Creating Tables with SQLite
  
  ### Adding Table Columns
  
  ### Issuing Queries
  
  ### Multiple Named Constructors
  
  ### Massaging DB Return Maps
  
  ### Turning Class Instances to Maps
  
  ### Implementing the Repository
  
  ### More on the Repository
  
  ### Type Annotations
  
  ### Casting Lists

## Type Design

  ### More on the Repository
  
  ### Abstract Classes
  
  ### The Need for Abstract Classes
  
  ### Why Abstract Classes?
  
  ### More on Abstract Classes
  
  ### Repository Interface Design
  
  ### Defining the Source
  
  ### Cache Definitions
  
  ### Lists of Sources and Caches
  
  ### Ultimate Reusability
  
  ### Quick Gotcha
  
  ### Another Quick Gotcha!
  
  ### FetchTopIds Implementation

## On Demand Widget Rendering

  ### App Setup
  
  ### A Touch of Boilerplate
  
  ### Data Fetching Concerns
  
  ### Solution Outline
  
  ### FutureBuilder in Action
  
  ### The Stories Provider
  
  ### Bloc Design
  
  ### Exposing Bloc Getters
  
  ### Wiring up the Stories Provider
  
  ### Bloc Testing
  
  ### Type Annotations Solve Problems
  
  ### Circular Progress Indicator
  
  ### Item Fetching Architecture
  
  ### Giant Gotcha with StreamBuilder
  
  ### Giant Gotcha Solution
  
  ### Implementing ScanStreamTransformer
  
  ### Finishing the ScanStreamTransformer
  
  ### Adding the Items Controller
  
  ### A Gotcha Around Streams? Impossibe!
  
  ### Single Transformer Application
  
  ### The ListView Tile
  
  ### StreamBuilder Setup
  
  ### Wrapping Up the FutureBuilder
  
  ### Double Gotcha!
  
  ### Stream Subscriptions
  
  ### Stream Subscription Fix
  
  ### Additional Streams
  
  ### A Laborious Refactor
  
  ### Result of Refactor
  
  ### Quick Debug Session
  
  ### Resolving Database Conflicts
  
  ### Building Story Tiles
  
  ### Comments Icon
  
  ### Applying Dividers with Height
  
  ### Loading Container Stand-in
  
  ### Building the Loading Container
  
  ### Showing the Loading Container
  
  ### Long-lived Cache Values
  
  ### Swipe to Refresh Indicator
  
  ### Implementing a Refresh Widget
  
  ### Clearing Database Tables
  
  ### Communicating a Future to onRefresh

## Navigation with Flutter

  ### Navigation in Flutter
  
  ### Map Based Routing
  
  ### OnGenerateRoute-Based Navigation
  
  ### OnGenereateRoute Implementation
  
  ### Navigating in Style!
  
  ### A PageRoute for NewsDetail
  
  ### A Scaffold in NewsDetail
  
  ### Parsing Route Settings
  
  ### The Comments Bloc Provider
  
  ### Comments Bloc Design
  
  ### More on Comments Bloc
  
  ### Recursive Data Fetching
  
  ### Quick Fix
  
  ### Connecting the Comments Provider
  
  ### Testing Recursive Fetching
  
  ### Consuming the Item Map
  
  ### Displaying the Story Title
  
  ### Text Styling
  
  ### Container Alignment
  
  ### Building the Comments List
  
  ### More Logic Extraction
  
  ### The Comment Widget
  
  ### Comment's FutureBuilder
  
  ### Showing Individual Comments
  
  ### Recursive Rendering
  
  ### Styling the Commment List
  
  ### Defaulting Null Values
  
  ### Handling Deleted Comments
  
  ### Nested Comments
  
  ### ListTile's ContentPadding Property
  
  ### Replacing Placeholder Characters
  
  ### Loading Containers for Comments
  
  ### App Wrapup
  
  ### Last Fix!

## Appendix One: Building Open Source with Dart

  ### Dart Local Installation
  
  ### Dart Install on Mac
  
  ### Editor Setup for Dart
  
  ### App Overview
  
  ### Folder and File Structure
  
  ### The PubSpec File
  
  ### Running Dart Files
  
  ### Program Design Methodology
  
  ### Class Creation
  
  ### Terminal Design
  
  ### Terminal Implementation
  
  ### Stdout and Stdin
  
  ### Import Statements
  
  ### Stdout Instance
  
  ### More on Import Statements
  
  ### Testing the Import Class
  
  ### Checking Operating System
  
  ### Clearing Windows Terminal
  
  ### Clearing Other Terminals
  
  ### Testing ClearScreen
  
  ### Collecting Input Over Stdin
  
  ### Option Class Fields
  
  ### Adding Dynamic Fields
  
  ### Printing Individual Options
  
  ### Testing Option Printing
  
  ### List Shortcomings
  
  ### Maps in Dart
  
  ### Refactor to Maps
  
  ### The Prompter Class
  
  ### Testing the Prompter
  
  ### Extracting the Terminal
  
  ### Var vs Final for Variables
  
  ### Final's Affect on Values
  
  ### Const's Dual Nature
  
  ### Const's Behavior by Type
  
  ### Marking Terminal as Const
  
  ### Private Variables
  
  ### Finishing Prompter
  
  ### Error Handling
  
  ### Asking Binary Questions
  
  ### Testing Binary Inputs
  
  ### Code Similarities
  
  ### Refactor for Code Reuse
  
  ### More on Private
  
  ### Central Lib File
  
  ### A Single Export Point
  
  ### A Relevant Example File
  
  ### Outstanding Project Config
  
  ### Uploading the Prompter Lib

## Apprendix Two: Building a Dart CLI

  ### App Overview
  
  ### Project Setup
  
  ### Importing Library Code
  
  ### Forcibly Exiting a Program
  
  ### Prompting for File Type
  
  ### Implementation Flow
  
  ### Working with the Current Directory
  
  ### Filtering Non-Files
  
  ### Filtering Non-Images
  
  ### Building Options from Images
  
  ### Testing Image Selection
  
  ### Converting Images
  
  ### The ConvertImage Function
  
  ### Reading File Contents
  
  ### Encoding to JPG or PNG
  
  ### Writing Files to the Hard Drive
  
  ### Returning the Image Name
  
  ### Testing Image Conversion
  
  ### Opening the Image

## References

- https://www.udemy.com/dart-and-flutter-the-complete-developers-guide/learn/v4/content
