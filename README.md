<details>
  <summary>What's the difference between @Controller and @RestController</summary><br>
## Purpose

This project contains the source code for a Java-based application that follows the Model-View-Controller (MVC) architecture and provides an API for various operations. Here's a brief overview of its purpose:

- `@Controller`: This annotation is used for creating controllers in the context of a traditional MVC web application. Controllers are responsible for handling requests and rendering views. They are typically associated with the frontend side of the application, and we use Thymeleaf for rendering views. As a result, returning data structures like `List<>` can lead to errors.

- `@RestController`: In contrast, this annotation is used to create controllers for building APIs. Unlike traditional controllers, `@RestController` doesn't render views on the frontend. Instead, it directly transforms data into JSON or XML format using Jackson or similar libraries.

### Response Type

- `@Controller`: Controllers annotated with `@Controller` typically return a view name. To return data directly, you would need to use the `@ResponseBody` annotation along with appropriate data structures.

- `@RestController`: All methods in `@RestController` are automatically annotated with `@ResponseBody`, meaning they return data in a format suitable for APIs.

## Class

One important class in this project is `ResponseEntity<List<String>>`. This class allows you to include additional information such as status codes and headers when returning a list of strings in response to an API request.

## Annotations

Here are some of the key annotations used in this project:

- `@Controller`: This annotation marks a class as a controller for handling requests in a traditional MVC application.

- `@RestController`: This annotation marks a class as a controller for building APIs. It automatically includes `@ResponseBody` for all its methods.

- `@ResponseBody`: This annotation is used to indicate that the return value of a method should be serialized directly to the HTTP response body.

- `@RequestMapping("/api/books")`: This annotation is used to set a specific base URL for all methods within the `BookController` class. In this case, all endpoints in this controller will start with `/api/books`.

- `@GetMapping("/search")`: This annotation specifies that the `getBookByName` method should handle HTTP GET requests at the `/api/books/search` URL. It also includes a `@RequestParam` annotation to capture request parameters, such as `name`.

```java
@Controller
@RestController
@ResponseBody
@RequestMapping("/api/books")
public class BookController {
    //...
    
    @GetMapping("/search")
    public String getBookByName(@RequestParam String name) {
        //...
    }
}
```
  
</details>

------------------------------------------------------------
