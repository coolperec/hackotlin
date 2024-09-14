[[kotlin course 09.09.2024]]

```Kotlin

```fun main()  
{  
    //https://www.youtube.com/watch?v=CC0qGXIn7QQ  
    //анонимная функция(выражение)  
//    val sum: (Int, Int) -> Unit = {x: Int, y: Int -> println(x + y)}  
//    (sum(6, 5))  
//    val factor = 5  
//    val MultiPlyBy: (Int) -> Int = {x: Int -> x * factor}  
//    println(MultiPlyBy(6))  
  
    val x = 5  
    val y = 2  
    val operation = {Value1: Int, Value2: Int -> Value1 * Value2}  
    calculate(x,y, operation)  
    calculate(x=2, y=3) {Value1, Value2 -> Value2 * Value1}  
    calculate(x=10, y=100){p1, p2-> p2 - p1}  
    calculate(x = 10, y =20, getOpeartion(operation = "multi"))  
}  
  
fun calculate(x:Int, y:Int, operation: (Value1:Int, Value2:Int) -> Int)  
{  
    println(operation(x,y))  
}  
  
fun getOpeartion(operation:String): (Int, Int) -> (Int)  
{  
    return when (operation)  
    {  
        "add" -> {x: Int, y:Int -> x + y}  
        "multi" -> {x: Int, y:Int -> x* y}  
        else -> {_, _ -> 0}//когда название аргумента нам не важны вместо них указывае подчеркивание  
    }  
}  
  
//функиця которая принимает или возвращяет выражение называется Фунцкия высшего порядка  
//так же видео было показано взаимадействие лямбды с классами, а также с функцияими Kotlinно я пока до это не дошел
