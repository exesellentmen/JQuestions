<details>
  <summary>What's the difference between @Controller and @RestController</summary><br>

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
