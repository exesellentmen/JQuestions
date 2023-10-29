<details>
  <summary>1. What's the difference between @Controller and @RestController</summary><br>

## Purpose

- `@Controller`: created for MVC application

- `@RestController`: created for API application

- `@Controller` will be handle on frontend side, by way of Thymeleaf, that why we get error if we try to return List<> for example

- `@RestController` will not handle on frontent side and will be transform to json by way of Jackson .json .xml

### Response Type

- `@Controller` typicaly return VIEW NAME, for return directly data we have to use ANNOTATION `@ResponseBody`

- `@RestController`: all methods already annotated `@ResponseBody`

### Class:

`ResponseEntity<List<String>>` - we can add status code and etc

### Annotations:

```java
@Controller
@RestController
@ResponseBody

@RequestMapping("/api/books")
public class BookController {
    //...
}    

@GetMapping("/search")
public String getBookByName(@RequestParam String name) {
    //...
}

```
  
</details>

------------------------------------------------------------

<details>
  <summary>
    2. Exceptions
  </summary><br>

`Exceptions` - is a message that we get after uncorrect app working

</details>

------------------------------------------------------------


<details>
  <summary>
    2.1 Exception hierarchy
  </summary><br>

1 Throwable: Это базовый класс для всех классов ошибок и исключений в Java.

    1.1 Error: Этот подкласс Throwable представляет серьезные ошибки, которые обычно невозможно обработать. Это внутренние ошибки JVM и другие критические ситуации.

        1.1.1 VirtualMachineError - Ошибки, связанные с JVM. 

        1.1.2 OutOfMemoryError - when we add a lot of objects wich garbage collector can't remove, because it very fast
        recursiveMethod - when we do deep recurs

        1.1.3 StackOverflowError - when we do deep recurs

        1.1.4 AssertionError - Сигнализирует об ошибке утверждения.

        ... 

    1.2 Exception: Это базовый класс для всех проверяемых исключений, которые могут и должны быть обработаны в приложении.

        1.2.1 RuntimeException: - for that exception we don't need to add try catch because it works automatically "unchecked exceptions." errors wich display in time of application running

            1.2.1.1 NullPointerException: Возникает, когда приложение пытается использовать объект по ссылке null.

            1.2.1.2 IndexOutOfBoundsException: Сигнализирует о том, что индекс вышел за границы массива или коллекции.

            1.2.1.3 ArithmeticException: Возникает при арифметических ошибках, таких как деление на ноль.
            
            1.2.1.4 IllegalArgumentException: problems with arguments

        1.2.2 IOException: Сигнализирует о проблемах ввода-вывода. Примеры: FileNotFoundException, EOFException.

        1.2.3 SQLException: Ошибки, связанные с доступом к базам данных.



</details>

------------------------------------------------------------
