# 🚀 Spring Boot 3 Generic Pagination & Sorting Infrastructure

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2-green)
![Architecture](https://img.shields.io/badge/Architecture-Clean-blue)

## 📖 Overview

This repository demonstrates an **Enterprise-Level Pagination and Sorting Architecture** implemented with **Spring Boot 3**.

Unlike standard implementations, this project utilizes **Java Generics (`<T>`)** and an **Abstract Base Controller** pattern to create a reusable, highly scalable infrastructure. It eliminates code duplication by centralizing pagination logic in a utility layer.

## 🏗️ Key Architectural Features

* **Generic Response Wrapper (`RestPageableEntity<T>`):** A standard JSON response format for all paginated endpoints.
* **Abstract Base Controller:** Common logic is encapsulated in a base class, allowing concrete controllers to inherit pagination capabilities automatically.
* **Utility Layer (`PagerUtil`):** Centralized mapping logic to convert request parameters into Spring Data `Pageable` objects.
* **DTO Pattern:** Strict separation between Entity and Data Transfer Objects.

## 🛠️ Project Structure

```text
src/main/java/com/example/pagination
├── controller/
│   ├── base/           # RestBaseController (The Brain 🧠)
│   └── impl/           # RestPersonnelController
├── util/               # PagerUtil (Helper Methods)
├── dto/                # Data Transfer Objects
├── entity/             # JPA Entities
├── repository/         # JPA Repositories
└── service/            # Business Logic Layer
💻 Code Highlights
1. Generic Base Controller Usage The logic is written once and used everywhere via inheritance.

Java
public class RestPersonnelController extends RestBaseController implements IRestPersonnelController {
    // Inherits pagination methods automatically!
}
2. Custom Pagination Response API responses are standardized:

JSON
{
  "content": [ ...data... ],
  "pageNumber": 0,
  "pageSize": 10,
  "totalElements": 150
}
⚙️ How to Run
Clone the repository:

Bash
git clone [https://github.com/efeerturk7/spring-boot-pageable.git](https://github.com/efeerturk7/spring-boot-pageable.git)
Configure application.properties with your PostgreSQL settings.

Run mvn spring-boot:run.

🤝 Contributing
Contributions are welcome!

📝 License
This project is MIT licensed.
