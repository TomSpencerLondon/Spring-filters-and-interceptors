## Spring Boot MVC

This is a practice app to understand Spring Filters

### Relevant Articles:
- [HandlerInterceptors vs. Filters in Spring MVC](https://www.baeldung.com/spring-mvc-handlerinterceptor-vs-filter)

#### Filters
Filters are part of the webserver and not the Spring framework.

#### Filters as they appear in the Spring boot logs
![Screenshot 2022-02-13 at 11 32 10](https://user-images.githubusercontent.com/27693622/153751033-9ef75f47-9c65-49bc-afa1-1e3535eb6730.png)

####Diagram of filters and interceptor request and responses:
![filters_vs_interceptors-1536x573](https://user-images.githubusercontent.com/27693622/153751099-9ef21446-0667-4529-a746-fcfa03393bc1.jpg)

#### Filters intercept requests before they reach the DispatcherServlet, making them ideal for coarse-grained tasks such as:

- Authentication
- Logging and auditing
- Image and data compression
- Any functionality we want to be decoupled from Spring MVC

#### HandlerIntercepors, on the other hand, intercept requests between the DispatcherServlet and our Controllers. This is done within the Spring MVC framework, providing access to the Handler and ModelAndView objects. This reduces duplication and allows for more fine-grained functionality such as:

- Handling cross-cutting concerns such as application logging
- Detailed authorization checks
- Manipulating the Spring context or model

#### Conclusion

The key takeaway is that with Filters, we can manipulate requests before they reach our controllers and outside of Spring MVC. 
Otherwise, HandlerInterceptors are a great place for application-specific cross-cutting concerns. 
By providing access to the target Handler and ModelAndView objects, we have more fine-grained control.