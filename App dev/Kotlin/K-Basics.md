- Advantages of Kotlin
	- has null safety
	- Use all Java libraries in Kotlin too
	- Kotlin has coroutines
	- Less code in Kotlin

> [!NOTE]
> - Oracle jdk need license and makes you pay when you need to commerically make a app, so use openJDks for it
- Uses camelcase
### Null Checking
- input string can be null
- we can't perform .toUppercase( ) or any fxns if string is null
- so we put ? after string
- or we can just use if statement
- and !! at the end of function like .toUppercase()!!
# Variables
- var can be changed later, val can't, so use var mostly
```kotlin
println(15/7)         // prints 2  (integer)
```
- to use float , gotta type F at the end of number
- floats takes 4 bytes
- double takes 8 bytes
- use float if space needs to be less
```kotlin
 fun main(){  
    println("I'm rat fucker")  
    var myVariable : Int = 5  
    println(myVariable)  
    myVariable=10  
    println("My variable now is $myVariable")  
    var v2: Boolean= true  
    v2= false  
    println(v2)  
  
    val a=15  
    val b=7  
    val result=a+b  
    println(result)  
    println(15/7)  
  
    val x: Float = 3F                  // Keep F at end  
    println("x: $x")  
    val y =4.56F  
    println("x + y : ${x+y}")  
    println("x / y : ${y/x}")  
    val z:Float =50.518478654138F       // compiler compresses it so use double  
    println(z)  
    val d= 5.518478654138              // double, more accurate  
    println(d)  
    println("x + y + z :${x+y+z}")  
  
    val r= 5.5f  
    var volume= 0.75 *3.14*r*r*r  
    println("The volume of sphere is: $volume")  
  
     var string= "this is example text"  
    println("The string is $string")  
    println("The string is ${string.toUpperCase().toLowerCase()}")  
    var name="Ramona"  
    println("My name is ${name.toUpperCase().reversed()}")  
    println(3>4||4>3&&4<=4)  
  
    if(a>b){  
        println("yipee")  
    }else if(b<a){  
        println("not yipee")  
    }else{  
        println("kys")  
    }  
    var num= if(a+b==14) 5 else 4  
    println(num)  
  
    var car= "racecar"  
    if(car==car.reversed()) println("The string $car is a palindrome")  
    else println("The string $car is not palindrome")  
  
    var userInput= readln()             // userInput can be null (nothing can be inputted)  
    println(userInput?.toUpperCase())    // can't find uppercase if the string is null so we put ?  
    println("You entered $userInput")  
  
    val integer1= readln()  
    if(integer1!=null)  
        println(integer1.toInt()-5)       // this line can crash if you input a string(consider it)  
  
    val myArray= arrayOf( "joe", 3 , "sup") // try to keep it homo  
    println(myArray)                         // prints giberish, like lang, type, address  
    println(myArray[0])  
    println(myArray[1])  
  
}
```
- Array can have any type
```kotlin
 val myArray= arrayof("hi", 3 , 5.697)            // can keep any type but keeping it same type is preferred
```
## Loops
```kotlin
fun main(){
val arr= arrayOf("hi", "sup", "guys?")  
    val l=arr.size  
    var i=0  
    while(i<l){  
        println(arr[i])  
        i++  
    }  
    println("Enter a number: ")  
	var userInput= readln()  
	var n=userInput.toInt()                     // or  var n= realLine()?.toInt()
	println("Lets count down from $n to 0" )  
	if(n!=null){  
	    var i=n  
	    while(i>=0){  
	        println(i)  
	        i--  
	    }  
	}
	println("Enter first no:")  
	var n1= readln()?.toInt()!!  
	println("Enter second no:")  
	var n2= readln()?.toInt()!!  
	var index=n2  
	var result=1  
	while(index>0){  
	    result= result*n1  
	    index--  
	}  
	println("$n1 to the power $n2 is $result")
	var myArray= arrayOf(1,5,6,3,4)  
	for (i in myArray){  
	    println(i)  
	}  
	for (i in 1..6){  
	    println(i)  
	}  
	for(i in 10 downTo 5 step 2) println(i)  
	for( i in 'a'..'z') println(i)
}
```
- It looks like
- ![[Pasted image 20241030144706.png]]
- ![[Pasted image 20241030150820.png]]
- if we have to input into an array
```kotlin
var myArray= arrayOf(1,5,6,3,4)  
var sum=0  
for (item in myArray){  
    sum+=item  
}  
println(sum)  
  
var sum1=0  
var average=0F  
var myArray2= Array<String>(5){"0"}      // val myArray2=Array<Int>()
println("Enter the 5 numbers:")  
for (i in 0..4)  
    myArray2[i]= readln()  
for(i in myArray2){  
    sum1+=i.toInt()  
}  
average=sum1.toFloat() /5  
println(average)
```
## List
- val of array can be changed during runtime but not list
- values of list- immutable 
- so just make a mutable list
- mutable list can change in size, unlike array , where ud have to create a new one if you want to change it's size
```kotlin
val array= arrayOf(1,2,3)  
val list= listOf(1,2,3)  
  
array[0]=10         // possible  
list[0]=10          //gives error
val list= mutableListOf(1,2,3)  
list[0]=10          // works  
list.add(4)         // can't do this in arrays
println(list)       // gives [10, 2, 3, 4]
list.remove(4)      // element
list.removeAt(1)    // at that index
 
val list= mutableListOf<Int>()  
for(i in 1..5){  
    var x= readln()?.toInt()  
    if(x!=null) list.add(x)  
}  
println(list)  
println("The list is: ")  
for(i in list) println(i)

val list= mutableListOf<Int>()  
println("Please enter the 5 numbers: ")  
for ( i in 1..5){  
    var x= readln()?.toInt()  
    if(x!=null)  list.add(x)  
}  
println("The numbers in reverse order are:")  
for(i in list.size-1 downTo 0) println(list[i])

// fibonacci  
println("Enter a number n>1:")  
val n= readln()?.toInt()  
val list= mutableListOf<Int>()   // or mutableListof(0,1)  starts the list with 0 and 1 already inside
if(n!=null){  
    list.add(0)                  // then we don't have to keep these
    list.add(1)  
    for (i in 2..n-1){  
        list.add(list[i-1]+list[i-2])  
    }  
}  
println(list)
```
## When
- if all 'if else ' statements depend on single variable use 'when'
- disadvantages
	- if there is another variable, we cannot use this (we can keep another if statement inside)
	- cannot execute several commands in single comparision (just use curly brackets)
```kotlin
val age= readlnOrNull()?.toInt()  
  
when(age){  
    in 0..6 -> {println("Your a kid")
                println("Go play with toys")}  
    in 7..17 -> println("Your a teen")  
    18 -> println("Finally 18! yay")  
    19,20 -> println("Your young adult")    // 19||20   (or)  
    in 21..65 -> println("Your an adult")  
    else -> println("Your old af fam")    // don't do this cuz it applies for -ve numbers too  
}
println("Where are you from?")  
val coun= readlnOrNull()  
when(coun){  
    "India"->println("namaste")  
    "USA" -> println("Sup")  
    "Germany"-> println("Hallo")  
    "Russia"-> println("privet")  
    else -> println("I don't know that")  
  
}
```
## Functions
```kotlin
fun main(){  
    printThreelines()  
    powerOf(3,4)  
}  
fun printThreelines(){  
    println("one")  
    println("two")  
    println("three")  
}  
fun powerOf(base:Int, exponent:Int){  
    var result=1  
    for(i in 1..exponent)  
        result*=base  
    println("The $base to the $exponent is $result")  
}

fun sumofval(start:Int, end:Int): Int{  
    var sum=0  
    for(i in start..end)  
        sum+=i  
    return sum  
}  
fun main(){  
    val pow= sumofval(1,10)  
    println("The sum is $pow")  
}

//
fun main(){  
    println(multiply(3,5))  
}  
fun multiply(a:Int, b:Int)= a*b

// find element in list
fun main(){  
    val list= listOf(1,5,8,93,7,6,2,0,4,3)  
    println("The list looks like this $list")  
    println("Search for this number: ")  
    val input= readln()?.toInt()!!                   // instead of !! use if(input!=null)
    val index=findIndex(list, input)  
    if(index>=0) println("The index is $index")      //"The index is ${findIndex(list,input)}"  
    else println("The element does not exist")  
}  
fun findIndex(list:List<Int>, a:Int):Int{  
    for(i in 0..list.size-1){               // use until if kotlin asks cuz calculation is inside
        if(a==list[i])                       // it should be reverse
            return i  
    }  
    return -1  
}
```
- if calculation inside range, use "until" keyword
```kotlin
for( i in 0 until list.size-1)             // list.size-1 is calculation
```
### vararg
- means we can have various no of parameters 
```kotlin
fun main(){  
    val arr= intArrayOf(10,20,60)          // can use only intArrayof and not arrayOf  
    val max= getMax(1,2,3,*arr,5,7,9,6,1,12,4)  
    println("The max is $max")  
}  
fun getMax(vararg numbers : Int ):Int{  
    var max=numbers[0]  
    for(num in numbers){  
        if(num>max) max=num  
    }  
    return max  
}
// alternating sum
fun main(){  
    val sum= alternatingSum(3,4,5,2,1,2,3)  
    println("The alternatin sum is $sum")    
}  
fun alternatingSum(vararg numbers:Int): Int{  
    val n=numbers.size  
    var sum=0  
    for(i in 0..n-1){  
        if(i%2==0) sum+=numbers[i]  
        else sum-=numbers[i]  
    }  
    return sum  
}
```
![[Pasted image 20241101161755.png]]
- default- if nothing is passed as parameter, the default one is takes automatically
```kotlin
fun main(){  
    searchFor("How to become a fish")  
    searchFor("How to become a shark", "Bing")  
}  
fun searchFor(search:String, searchEngine:String= "Google"){    // default  
    println("Search for $search on $searchEngine")  
}
```
- if you got a lot of parameter you can just specify them and keep in any order
```kotlin
searchFor(searchEngine= "Bing", search= "How to become fish")
// not in order but works
```
### Extension Functions
- can extend a function like those .size functions-
- we use "this" keyword
- (dk wtf the difference is, it's like normal function? )
```kotlin
fun main(){  
    println("Enter a number:")  
    val input= readln()?.toInt()  
    if(input!=null){  
        if(input.isPrime()) println("A prime")  
        else println("Not prime")  
    }  
}  
fun Int.isPrime():Boolean{  
    for( i in 2 until this-1){  
        if (this%i==0) return false  
    }  
    return true  
}
```
![[Pasted image 20241101165534.png]]
## Classes
- class- blueprint/ template for methods for variables
- objects- instance of class

> [!NOTE]
> > CTRL + hover over a class and kotlin shows it's implementation
- init method- constructor
```kotlin
fun main(){  
    val myRect= Rectangle(5.6,6.0)  
    println("The rectangle area is ${myRect.area()}")  
    println("The rect perimeter is ${myRect.perimeter()}")  
    println(myRect.isSquare())  
      
    val myCircle= Circle(4.3)         // kept all the print statements inside init method  
    val myTria= Triangle(3.0,4.0,5.0)  
}
import kotlin.math.sqrt  
  
class Triangle(  
    val a:Double,  
    val b:Double,  
    val c:Double  
) {  
    init{  
        println("A triangle of sides $a , $b, $c is created")  
        println("The perimeter of triangle is ${perimeter()}")  
        println("The area of triangle is ${area()}")  
    }  
  
    fun area()= sqrt((perimeter()/2)*((perimeter()/2)-a)*((perimeter()/2)-b)*((perimeter()/2)-c))  
    fun perimeter()= a+b+c  
}

class Rectangle(  
    val a:Double,  
    val b: Double  
) {  
    init{  
        println("Rectable created with a= $a and b=$b")  
    }  
    fun area()= a*b  
    fun perimeter()= 2*a + 2*b  
    fun isSquare()= a==b  
} 

class Circle(  
    val r:Double  
) {  
    val pi= 3.141592  
    init {  
        println("A circle of radius $r is created")  
        println(area())  
        println(perimeter())  
        println("The circle radius larger than pi? ${isLarge()}")  
    }  
    fun area()= pi*r*r  
    fun perimeter()= 2* pi*r  
    fun isLarge()= r>pi  
}
```
### Inheritance
- to make a class to be inherited from, make it open class
- to make "Shape" class inheritable, make it open class
```kotlin
fun main(){  
    val myCir1= Circle(3.0)  
    myCir1.changeName("Peter circle")   // inherited from shape class  
    println(myCir1.name)  
}

open class Shape(  
    var name: String  
) {  
    init{  
        println("A superclass!!")  
    }  
    fun changeName(newName:String){  
        name=newName  
    }  
}

class Rectangle(  
    val a:Double,  
    val b: Double  
):Shape("Rectangle") {  
    init{  
        println("$name created with a= $a and b=$b")  
    }  
    fun area()= a*b  
    fun perimeter()= 2*a + 2*b  
    fun isSquare()= a==b   
}

class Circle(  
    val r:Double  
) :Shape("Circle"){  
    val pi= 3.141592  
    init {  
        println("A $name of radius $r is created")  
        println("The $name area is ${area()}")  
        println("The $name perimeter is ${perimeter()}")  
        println("The $name radius larger than pi? ${isLarge()}")  
    }  
    fun area()= pi*r*r  
    fun perimeter()= 2* pi*r  
    fun isLarge()= r>pi  
}

import kotlin.math.sqrt  
class Triangle(  
    val a:Double,  
    val b:Double,  
    val c:Double  
):Shape("Triangle") {  
    init{  
        println("A $name of sides $a , $b, $c is created")  
        println("The perimeter of $name is ${perimeter()}")  
        println("The area of $name is ${area()}")  
    }  
  
    fun area()= sqrt((perimeter()/2)*((perimeter()/2)-a)*((perimeter()/2)-b)*((perimeter()/2)-c))  
    fun perimeter()= a+b+c  
}
```
- when inherited, the super class excuted first ![[Pasted image 20241101172337.png]]
## Visibility modifiers
- by default- public 
- private- only that class can access it
- protected- that class and the classes that inherit this class can access 
- U can make both functions and variables as private/ protected( it's not limited to just variables)
- make the pi from above as private
```kotlin
private val pi = 3.141592  
protected fun changeName(newName:String){              // wrong but just keeping for syntax
        name=newName  
    }  
```
- U can make private constructors ( it makes objects of circle class only within circle class, nobody wants it)
	 ![[Pasted image 20241101173911.png]]
## Abstract class
- only purpose of it so that other classes inherit from it (can't have abstract objects)

> [!NOTE] Override
> The class which inherits from abstract class must override all the abstract class fxns
> CTRL + O to see which classes to overwrite
- if we remove, area and perimeter from Rectangle class
	- ![[Pasted image 20241101195850.png]]
	- the following error occurs
	- ![[Pasted image 20241101195924.png]]
- the code
```kotlin
abstract class Shape(  
    var name: String  
) {  
    init{  
        println("A superclass!!")  
    }  
     fun changeName(newName:String){                    // normal fxn  
        name=newName  
    }  
  
    abstract fun area():Double                         // abstact fxn  
    abstract fun perimeter():Double  
}

class Rectangle(  
    val a:Double,  
    val b: Double  
):Shape("Rectangle") {  
    init{  
        println("$name created with a= $a and b=$b")  
    }  
    override fun area()= a*b  
    override fun perimeter()= 2*a + 2*b  
    fun isSquare()= a==b  
}

import kotlin.math.sqrt  
  
class Triangle(  
    val a:Double,  
    val b:Double,  
    val c:Double  
):Shape("Triangle") {  
    init{  
        println("A $name of sides $a , $b, $c is created")  
        println("The perimeter of $name is ${perimeter()}")  
        println("The area of $name is ${area()}")  
    }  
  
    override fun area()= sqrt((perimeter()/2)*((perimeter()/2)-a)*((perimeter()/2)-b)*((perimeter()/2)-c))  
    override fun perimeter()= a+b+c  
}

class Circle(  
    val r:Double  
) :Shape("Circle"){  
    private val pi= 3.141592  
    init {  
        println("A $name of radius $r is created")  
        println("The $name area is ${area()}")  
        println("The $name perimeter is ${perimeter()}")  
        println("The $name radius larger than pi? ${isLarge()}")  
    }  
    override fun area()= pi*r*r  
    override fun perimeter()= 2* pi*r  
    fun isLarge()= r>pi  
}
```
## Constructors and Fxn overloading
- overriding - from abstract classes
- overloading - different parameters (they must be unique in either type or number)
```kotlin
class Rectangle(  
    val a:Double,  
    val b: Double  
):Shape("Rectangle") {  
  
    constructor(a:Double): this(a,a)           // constructor
    constructor(a:Int, b:Int): this (a.toDouble(), b.toDouble())  // overloading 
  
    init{  
        println("$name created with a= $a and b=$b")  
    }  
    override fun area()= a*b  
    override fun perimeter()= 2*a + 2*b  
    fun isSquare()= a==b  
}
```
- comparing areas 
	- ![[Pasted image 20241101223954.png]]
	- ![[Pasted image 20241101223611.png]]
	- ![[Pasted image 20241101223647.png]]
## Singleton
- (in above, pi is instantiated whenever a circle object in instantiated , but we only need pi to be initialized once)
- like a class but there's only single instance of that
- you can put variables and functions in this object
	- ![[Pasted image 20241101225138.png]]
- ![[Pasted image 20241101225343.png]]
- we usually write them in all capital
- ![[Pasted image 20241101225456.png]]
```kotlin
object ImportantNumbers {  
    val PI= 3.141592  
}
class Circle(  
    val r:Double  
) :Shape("Circle"){  
    constructor(diameter:Int) : this((diameter/2).toDouble())  
    init {  
        println("A $name of radius $r is created")  
        println("The $name area is ${area()}")  
        println("The $name perimeter is ${perimeter()}")  
        println("The $name radius larger than pi? ${isLarge()}")  
    }  
    override fun area()= ImportantNumbers.PI*r*r        // here
    override fun perimeter()= 2* ImportantNumbers.PI*r  
    fun isLarge()= r>ImportantNumbers.PI  
}
```
- h/w question
	- ![[Pasted image 20241101234017.png]]
	- ![[Pasted image 20241101234358.png]]
## Companion object
- class with singleton behavior which we can still create instances for specific fxns and variables
- basically, we don't have to make a instance of object to call fxns inside it, we can just call them
```kotlin
import kotlin.random.Random  
  
class Circle(  
    val r:Double  
) :Shape("Circle"){  
    constructor(diameter:Int) : this((diameter/2).toDouble())  
  
    companion object{  
        fun randomCircle():Circle{  
            val radius= Random.nextDouble(1.0,10.0)  
            return Circle(radius)  
        }  
    }  
    init {  
        println("A $name of radius $r is created")  
        println("The $name area is ${area()}")  
        println("The $name perimeter is ${perimeter()}")  
        println("The $name radius larger than pi? ${isLarge()}")  
    }  
    override fun area()= ImportantNumbers.PI*r*r  
    override fun perimeter()= 2* ImportantNumbers.PI*r  
    fun isLarge()= r>ImportantNumbers.PI  
}
fun main(){  
    val circle= Circle.randomCircle()  
}
```
- here focus on main fxn
- we don't need an instance of circle object to access a function inside
- normally we'd need
```kotlin
val circle1= Circle(5.0)
circle1.randomCircle()                // don't need all this , also this shows error
```
## Anonymous class
- nested class with no name
- useful when making an instance of an object with certain “extras” such as overriding methods of a class or interface, without having to actually subclass a class
```kotlin
abstract class Shape(  
    var name: String  
) {  
    constructor(name:String, vararg dimensions:Double):this(name){  //added
    }    
    init{  
        println("A superclass!!")  
    }  
     fun changeName(newName:String){                    
        name=newName  
    }  
  
    abstract fun area():Double                           
    abstract fun perimeter():Double  
}

fun main(){  
    val a=3.0  
    val b=4.0  
    val height= 2.0  
    val parallelogram=object: Shape("Parallelogram",a,b,height){    // creating ananoymous class with " object:"
        init{  
            println("Parallelogram created with a=$a, b=$b and height=$height")  
            println("The area is ${area()}")  
            println("The perimeter is ${perimeter()}")  
            println("Is parallelogram rectangle? ${isRectangle()}")  
        }  
        override fun area(): Double {  
            return a*height  
        }  
  
        override fun perimeter(): Double {  
            return 2*a+2*b  
        }  
        fun isRectangle():Boolean = (height==b)  
    }  
}
// for trapezium
fun main(){  
    val a=2.0  
    val b=4.0  
    val c=1.5  
    val d=1.7  
    val height= 2.5  
    val trapezium = object :Shape("Trapezium", a,b,c,d,height){    // use object:
        init {  
            println("A trapezium of $a, $b, $c, $d , $height is created")  
            println("The area is ${area()}")  
            println("The perimeter is ${perimeter()}")  
            println("Is it equilateral? ${isEquilateral()}")  
        }  
        override fun area(): Double= (a+b)*height/2.0  
  
        override fun perimeter(): Double =a+b+c+d  
        fun isEquilateral():Boolean = c==d  
    }  
}
```
## Exceptions
- throw error and catch the error
- Exceptions crash the program if not handled properly
```kotlin
fun main(){  
    val input= readLine()?.toInt()  
}
```
- here if string is inputted instead of number (can't convert string to integer) , **NumberFormatException** occurs 
- hover over to see what exception it throws ( or CRTL+Q )
	- ![[Pasted image 20241102210156.png]]
```kotlin
fun main(){  
    println("Enter a number:")  
    val input= try{  
        readln()?.toInt()  
    }catch (e:NumberFormatException){  
        0  
    }finally {  
        println("This runs whether there is exception or not")  
    }  
    println("You've entered $input")  
}
```
- in the above ex
	- try- where exception may occur
	- catch- if exception occur, this executes
	- finally- executes regardless exception occurs or not 
- exception is superclass 
- so in above code we can just write 
```kotlin
catch (e:Exception){       //still works but go with NumberFormatException  
 0
```
## Create own Exception
- Exception is a super class
- to create an exception, make a class
```kotlin
fun main(){  
    val result= try{  
        divide(5.0, 0.0)  
    }catch (e:DivisionByZeroException){  
        0.0  
    }  
    println("The result is $result")  
}  
  
class DivisionByZeroException(): Exception("You cannot divide by zero, choose another number") {       
    // DivisionByZeroException() class inheriting Exception() class  
    // the message in brackets in important
    }  
fun divide(a:Double, b:Double): Double{  
    if(b==0.0){  
        throw DivisionByZeroException()  
    }  
    return a/b  
}
```

```kotlin
```

```kotlin
```

```kotlin
```