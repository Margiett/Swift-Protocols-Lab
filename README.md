
## Protocols Lab

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link of the pull request on Canvas and submit


<br>

> Questions adapted from [Swift student lessons: 4 - Tables and Persistence -> 1 - Protocols](https://developer.apple.com/go/?id=app-dev-swift-student)

## Question 1

a. Create a `Human` class with two properties:
- `name` of type String
- `age` of type Int.
```
class Human  {
var name: String 
var age: Int 
}
```
Then create an initializer for the class and create two `Human` instances.

```
class Human {
var age: Int
var name: String
init(name: String, age: Int) {
self.name = name
self.age = age
}
}

// creating the instances 
var Margiett = Human(name: Margiett, age: 27)
var Xiomara = Human(name: Xiomara, age: 25)
```
b. Make the `Human` class adopt the CustomStringConvertible protocol. Then print both of your previously initialized
`Human` objects.
```
class Human: CustomStringConvertible {
var age: Int
var name: String

init(name: String, age: Int){
self.name = name
self.age = age
}

var description: String {
return "The person's name is \(name) and they are \(age) years young"
}
}

var human1 = Human(name: "Margiett", age: 27)
var zarriah = Human(name: "Xiomara", age: 27)

print("human1")
print("Xiomara")

```
c. Make the `Human` class adopt the Equatable protocol. Two instances of `Human` should be considered equal
if their names and ages are identical to one another. Print the result of a boolean expression
evaluating whether or not your two previously initialized `Human` objects are equal to eachother
(using ==). Then print the result of a boolean expression evaluating whether or not your two
previously initialized `Human` objects are not equal to eachother (using !=).

My Answer:

```
class Human: CustomStringConvertible, Equatable {
    static func == (firstHuman: Human, secondHuman: Human) -> Bool {
        return firstHuman.name == secondHuman.name && firstHuman.age == secondHuman.age
    }
    var age: Int
    var name: String
    
    var description: String {
            return "The person's name is \(name) and they both are \(age) years young"
        }
        
    init(name: String, age: Int){
        self.name = name
        self.age = age
    }
}


var human1 = Human(name: "Margiett", age: 27)
var Xiomara = Human(name: "Xiomara", age: 27)

print(human1)
print(Xiomara)


if human1 == Xiomara {
    print("They are the same person")
}else{
    print("These are two different people")
}
```



d. Make the `Human` class adopt the `Comparable` protocol. One `Human` is greater than another `Human` if its age is bigger. Create another
three instances of a `Human`, then create an array called people of type [`Human`] with all of the
`Human` objects that you have initialized.

Create a new array called sortedPeople of type [`Human`] that is the people array sorted by age.

</br> </br>

My Answer:

```
class Human: CustomStringConvertible, Comparable {
    static func == (firstHuman: Human, secondHuman: Human) -> Bool {
        return false
    }
    
var name: String
var age: Int

static func > (firstHuman: Human, secondHuman: Human) -> Bool {
return firstHuman.age > secondHuman.age
}


static func < (firstHuman: Human, secondHuman: Human) -> Bool {
return firstHuman.age < secondHuman.age
}

var description: String {
return "The person's name is \(name) and they are \(age) years young"
}

    init?(name: String, age: String){
self.name
self.age
    
    return nil
    }
}
var human1 = "Margiett"
var human2 = "Xiomara"

//var human1 = Human(name: "Margiett", age: 27)
//var xiomara = Human(name: "Xiomara", age: 27)

if human1 < human2 {
    print("\(human1) is older then \(human2)")
} else {
    print("\(human2) is older")
}
```


## Question 2

a. Create a protocol called `Vehicle` with two requirements:
- a nonsettable `numberOfWheels` property of type Int,
- a function called drive().

```
protocol Vehicle{
 var numWheels : Int { get }

func drive()
}
```

b. Define a `Car` struct that implements the `Vehicle` protocol. `numberOfWheels` should return a value of 4,
and drive() should print "Vroom, vroom!" Create an instance of `Car`, print its number of wheels,
then call drive().

My Answer:
```
protocol Vehicle{
 var numWheels : Int { get }

func drive()
}

struct Car: Vehicle{

var numWheels: Int {
return 4
}

func drive() {
print("vroom, vroom")
    
}

}

var Onecar = Car()
Onecar.drive()
```

c. Define a Bike struct that implements the `Vehicle` protocol. `numberOfWheels` should return a value of 2,
and drive() should print "Begin pedaling!". Create an instance of Bike, print its number of wheels,
then call drive().

</br> </br>

```
// Define a Bike struct that implements the `Vehicle` protocol. `numberOfWheels` should return a value of 2,

struct Bike: Vehicle {
var numberOfWheels: Int {
    return 2}
drive() should print "Begin pedaling!
func drive(){
print("Begin pedaling!")
    }

}

//Create an instance of Bike, print its number of wheels, then call drive()

var instanceOfCar: Car {
.init(numberOfWheels: 4) 

print(instanceOfCar.numberOfWheels)
instanceOfCar.drive()

struct Bike: Vehicle {
    var numberOfWheels: Int = 2
    func drive() {
        print("Begin Pedaling!!")
    }
}
var instanceOfBike: Bike{
    .init(numberOfWheels: 2)
}
print(instanceOfBike.numberOfWheels)
instanceOfBike.drive()



```


## Question 3
// Given the below two protocols, create a struct for penguin(a flightless bird) and an eagle.

Give your structs some properties and have them conform to the appropriate protocols.

```swift
protocol Bird {
 var name: String { get }
 var canFly: Bool { get }
}

protocol Flyable {
 var airspeedVelocity: Double { get }
}
```

</br> </br>

## Question 4

a. Create a protocol called `Transformation`.  The protocol should specify a mutating method called transform

b. Make an enum called `SuperHero` that conforms to `Transformation` with cases `notHulk` and `hulk`

c. Create an instance of it named `bruceBanner`. Make it so that when the transform function is called that bruceBanner turns from
`.notHulk` to `.hulk.``

```swift
enum SuperHero: Transformation {
    // write code here.
}

// Example Output:
var bruceBanner = SuperHero.notHulk

bruceBanner.transform() . // hulk

bruceBanner.transform()  // notHulk
```

</br> </br>


## Question 5

a. Create a protocol called `Communication`
```
protocol Communitcation{

}
```

b. Give it a property called `message`, of type String, and assign it an explicit getter.

```
protocol Communication {
var message: String { get }
}
```

c. Create three Classes. `Cow`, `Dog`, `Cat`.
```
protocol Communitaction { 
var message: String { get }
}
class Cow{
}

class Dog{
}

class Cat {
}
```
d. Have your three classes conform to `Communication`
```
protocol Communication {
var message: String { get }
}

class Cow: Communication{
}

class Dog: Communication{
}

class Cat: Communication{
}
```
e. `message` should return a unique message for each animal when talk is called.

```
protocol Communication {
var message: String { get }
}

class Cow: Communication{
var message: String {
return "MOOOO MOOO MOOO"
    }
}

class Dog {
var message {
    return "ROOF ROOF"
}
}

class Cat {
var message: String {
return "MEOW MEOW"
}
}
```

f. Put an instance of each of your classes in an array.

```
protocol Communication {
var message: String { get }
}

class Cow: Communication{
var message: String {
return "MOOOO MOOO MOOO"
}
}

class Dog: Communication{
var message {
return "ROOF ROOF"
}
}

class Cat: Communication{
var message {
return "MEOW MEOW"
}
}

var mooMooAnimal = Cow.Communication
var bestAnimalEver = Dog.Communication
var meowMeowAnimal = Cat.Communication

var arrayOfAnimals = [mooMooAnimal, bestAnimalEver, meowMeowAnimal]
```

g. Iterate over the array and have them print their `message` property


## Question 6

The HeartRateReceiver class below represents a very simplified example of a class dedicated to receiving information from fitness tracking hardware with monitoring heart rate. The function startHeartRateMonitoringExample will generate random heart rates and assign them to currentHR, simulating how an instance of HeartRateReceiver may pick up on new heart rate readings at specific intervals.

HeartRateViewController below is a view controller that will present the heart rate information to the user. Throughout the exercises below you'll use the delegate pattern to pass information from an instance of HeartRateReceiver to the view controller so that anytime new information is obtained it is presented to the user.

```swift
class HeartRateReceiver {
    var currentHR: Int? {
        didSet {
            if let currentHR = currentHR {
                print("The most recent heart rate reading is \(currentHR).")
            } else {
                print("Looks like we can't pick up a heart rate.")
            }
        }
    }

    func startHeartRateMonitoringExample() {
        for _ in 1...10 {
            let randomHR = 60 + Int.random(in: 0...15)
            currentHR = randomHR
            Thread.sleep(forTimeInterval: 2)
        }
    }
}

class HeartRateViewController: UIViewController {
    var heartRateLabel: UILabel = UILabel()
}
```

First, create an instance of HeartRateReceiver and call startHeartRateMonitoringExample. Notice that every two seconds currentHR get set and prints the new heart rate reading to the console.

In a real app, printing to the console does not show information to the user. You need a way of passing information from the HeartRateReceiver to the HeartRateViewController. To do this, create a protocol called HeartRateReceiverDelegate that requires a method heartRateUpdated(to bpm:) where bpm is of type Int and represents the new rate as beats per minute. Since playgrounds read from top to bottom and the two previously declared classes will need to use this protocol, you'll need to declare this protocol above the declaration of HeartRateReceiver.

Now make HeartRateViewController adopt the protocol you've just created. Inside the body of the required method you should set the text of heartRateLabel and print "The user has been shown a heart rate of <INSERT HEART RATE HERE>."

Now add a property called delegate to HeartRateReceiver that is of type HeartRateReceiverDelegate?. In the didSet of currentHR where currentHR is successfully unwrapped, call heartRateUpdated(to bpm:) on the delegate property.

Finally, return to the line of code just after you initialized an instance of HeartRateReceiver. Initialize an instance of HeartRateViewController. Then, set the delegate property of your instance of HeartRateReceiver to be the instance of HeartRateViewController that you just created. Wait for your code to compile and observe what is printed to the console. Every time that currentHR gets set, you should see both a printout of the most recent heart rate, and the print statement stating that the heart rate was shown to the user.
