Class = Template, Object = Hasilnya

class Car {

}

### Class
![[Pasted image 20260209132229.png]] 

### Defining Objects
![[Pasted image 20260209132408.png]]


### Constructor?
Constructor itu biasanya sesuatu yang dijalankan pertama kali ketika pembuatan objek itu dibuat (Inisiasi nilai awal)


Demo.kt
package oop_00000106140_DymasiusRendragraha.week02  
  
fun main(){  
//    val myCar = Car("Mobilio", -20);  
//    myCar.drive();  
    val obj1 = Car("Mobilio", -10);  
    val a = "Kotlin"  
    val b = "Kotlin"  
    println(a === b);  
  
    for (i in 1..3)  
        print(i)  
  
    println("${cal(10, 20)}")  
  
    val name: String? = null  
    val length = name?.length ?: -1  
    println(length)  
}  
  
fun cal(a: Int, b: Int) = a + b

car class
package oop_00000106140_DymasiusRendragraha.week02  
  
class Car (  
    val brand: String,  
    var speed: Int  
) {  
    //Properties (State)  
//    var brand: String = ""  
//    var speed: Int = 0  
  
    init {  
        println("Car $brand, speed $speed created!")  
  
        if(speed < 0) {  
            speed = 0;  
            println("Error speed negative, setting speed to 0!");  
        }    }  
    var color: String = "blue"  
  
    fun drive(){  
        speed += 10  
        println("Drive Speed: $speed")  
    }}

