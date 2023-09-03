In Spring Boot, the typical codebase is structured as controller -> service -> repository, where each layer consists of one or more beans, and each bean contains one or more methods. Methods in a bean may not really have a relationship with each other: a bean representing a service object is an object just because everything in Java is an object, and methods that hold business or domain logic need to live somewhere. 

Moving this logic wholesale into a serverless implementation might look like this: the entry point of a Lambda can be thought of as the controller layer, which transforms the data and gives it to a service layer that holds the domain logic. The question: where does the service layer live? Should all the business logic relating to a particular domain be housed together in some kind of service object, like it typically is in Spring Boot or Rails?

Probably not. A service object isn't really object-oriented in the sense that object-oriented programming encapsulates state and behaviour. If a particular bit of domain logic is used by exactly one lambda, why not put the domain logic together with the lambda, instead of with other bits of logic from the same domain? Yes, this means that the business logic is now spread out in a few places, but the benefit is that all the code that is executed in one lambda is now collocated. If you move or delete the lambda, all the associated business logic goes with it.

This really needs a drawing or two.

-----

Static variables on a lambda :)