# 📘 Lesson 1: Spring Boot 3 Foundation

> ชั่วโมงที่ 1-2: พื้นฐาน Spring Boot 3 และ Dependency Injection

---

## 🎯 วัตถุประสงค์การเรียนรู้

หลังจากเรียนจบบทเรียนนี้ คุณจะสามารถ:
- ✅ เข้าใจความแตกต่างระหว่าง Spring Boot 3 และ 2.x
- ✅ สร้างโปรเจ็กต์ Spring Boot 3 ด้วย Spring Initializer
- ✅ เข้าใจ Jakarta EE และการเปลี่ยนแปลงจาก javax
- ✅ ใช้งาน Dependency Injection และ IoC Container
- ✅ กำหนดค่าแอปพลิเคชันด้วย Properties/YAML

---

## 📚 เนื้อหาการเรียน

### 1. Spring Boot 3 Overview

#### ความแตกต่างหลักระหว่าง Spring Boot 3 vs 2.x

| Feature | Spring Boot 2.x | Spring Boot 3.x |
|---------|----------------|-----------------|
| Java Version | Java 8+ | Java 17+ |
| Jakarta EE | javax.* | jakarta.* |
| Spring Framework | 5.x | 6.x |
| Observability | Micrometer | Enhanced Micrometer + Tracing |
| Native Image | Experimental | Production Ready |

#### สิ่งสำคัญที่ต้องรู้

1. **Java 17 Baseline** 🎯
   - Spring Boot 3 ต้องการ Java 17 ขึ้นไป
   - รองรับ Java 21 Features

2. **Jakarta EE Migration** 🔄
   ```java
   // Spring Boot 2.x
   import javax.servlet.http.HttpServletRequest;
   import javax.persistence.Entity;
   
   // Spring Boot 3.x
   import jakarta.servlet.http.HttpServletRequest;
   import jakarta.persistence.Entity;
   ```

3. **GraalVM Native Image Support** 🚀
   - Build แอปพลิเคชันเป็น Native Binary
   - เริ่มต้นเร็วขึ้น, ใช้ Memory น้อยลง

---

### 2. สร้างโปรเจ็กต์ Spring Boot 3

#### ขั้นตอนการสร้างด้วย Spring Initializer

1. เข้า [start.spring.io](https://start.spring.io)
2. เลือก Configuration:
   - **Project**: Maven
   - **Language**: Java
   - **Spring Boot**: 3.2.x (Latest Stable)
   - **Java**: 21
   - **Packaging**: Jar

3. เพิ่ม Dependencies:
   - Spring Web
   - Spring Boot DevTools
   - Lombok (Optional)

4. Generate และ Download โปรเจ็กต์

#### โครงสร้างโปรเจ็กต์

```
my-spring-boot-app/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/demo/
│   │   │       └── DemoApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── static/
│   │       └── templates/
│   └── test/
│       └── java/
├── pom.xml
└── README.md
```

#### Main Application Class

```java
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DemoApplication {
    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

---

### 3. Dependency Injection & IoC Container

#### IoC (Inversion of Control) คืออะไร?

- **Traditional Approach**: Object สร้าง dependencies ของมันเอง
- **IoC Approach**: Container สร้างและจัดการ dependencies ให้

#### Spring Stereotypes Annotations

##### 1. @Component
```java
@Component
public class EmailService {
    public void sendEmail(String message) {
        System.out.println("Sending email: " + message);
    }
}
```

##### 2. @Service
```java
@Service
public class UserService {
    public User createUser(String name) {
        // Business logic
        return new User(name);
    }
}
```

##### 3. @Repository
```java
@Repository
public class UserRepository {
    public void save(User user) {
        // Database operations
    }
}
```

#### Dependency Injection Methods

##### 1. Constructor Injection (✅ แนะนำ)
```java
@Service
public class OrderService {
    private final EmailService emailService;
    private final UserRepository userRepository;
    
    // Constructor Injection - Best Practice
    public OrderService(EmailService emailService, 
                       UserRepository userRepository) {
        this.emailService = emailService;
        this.userRepository = userRepository;
    }
    
    public void placeOrder(Order order) {
        userRepository.save(order.getUser());
        emailService.sendEmail("Order placed!");
    }
}
```

**ข้อดี:**
- Immutable (ใช้ final ได้)
- ทดสอบง่าย
- Null-safe
- ไม่ต้องใช้ @Autowired (Spring 4.3+)

##### 2. Field Injection (❌ ไม่แนะนำ)
```java
@Service
public class OrderService {
    @Autowired
    private EmailService emailService;
    
    @Autowired
    private UserRepository userRepository;
}
```

**ข้อเสีย:**
- ไม่ immutable
- ทดสอบยาก
- อาจเป็น null ได้

##### 3. Setter Injection (⚠️ ใช้เฉพาะกรณีพิเศษ)
```java
@Service
public class OrderService {
    private EmailService emailService;
    
    @Autowired
    public void setEmailService(EmailService emailService) {
        this.emailService = emailService;
    }
}
```

---

### 4. Configuration with Properties/YAML

#### application.properties
```properties
# Server Configuration
server.port=8080
server.servlet.context-path=/api

# Application Name
spring.application.name=my-spring-boot-app

# Logging
logging.level.root=INFO
logging.level.com.example=DEBUG

# Custom Properties
app.name=My Application
app.version=1.0.0
```

#### application.yml (แนะนำ - อ่านง่ายกว่า)
```yaml
server:
  port: 8080
  servlet:
    context-path: /api

spring:
  application:
    name: my-spring-boot-app

logging:
  level:
    root: INFO
    com.example: DEBUG

app:
  name: My Application
  version: 1.0.0
```

#### อ่านค่า Configuration

##### 1. @Value
```java
@Service
public class AppInfoService {
    @Value("${app.name}")
    private String appName;
    
    @Value("${app.version}")
    private String appVersion;
    
    public String getInfo() {
        return appName + " v" + appVersion;
    }
}
```

##### 2. @ConfigurationProperties (✅ แนะนำสำหรับ Multiple Properties)
```java
@Configuration
@ConfigurationProperties(prefix = "app")
public class AppProperties {
    private String name;
    private String version;
    
    // Getters and Setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    
    public String getVersion() { return version; }
    public void setVersion(String version) { this.version = version; }
}
```

```java
@Service
public class AppInfoService {
    private final AppProperties appProperties;
    
    public AppInfoService(AppProperties appProperties) {
        this.appProperties = appProperties;
    }
    
    public String getInfo() {
        return appProperties.getName() + " v" + appProperties.getVersion();
    }
}
```

---

### 5. Bean Lifecycle และ Scopes

#### Bean Scopes

| Scope | Description |
|-------|-------------|
| **singleton** (default) | Bean เดียวต่อ 1 Spring Container |
| **prototype** | สร้าง Bean ใหม่ทุกครั้งที่ request |
| **request** | Bean ใหม่ต่อ HTTP Request (Web only) |
| **session** | Bean ใหม่ต่อ HTTP Session (Web only) |

```java
@Service
@Scope("prototype")
public class PrototypeService {
    // สร้างใหม่ทุกครั้ง
}
```

#### Lifecycle Callbacks

```java
@Component
public class DatabaseConnection {
    
    @PostConstruct
    public void init() {
        System.out.println("Initializing database connection...");
    }
    
    @PreDestroy
    public void cleanup() {
        System.out.println("Closing database connection...");
    }
}
```

---

## 💻 Lab Exercise

### ✏️ แบบฝึกหัด: สร้าง Simple Library Service

สร้าง Spring Boot Application ที่มี:

1. **BookService** - จัดการหนังสือ
2. **NotificationService** - ส่งการแจ้งเตือน
3. **BookRepository** - จัดเก็บข้อมูล (ใช้ in-memory List)

#### Book.java
```java
public class Book {
    private Long id;
    private String title;
    private String author;
    
    // Constructor, Getters, Setters
}
```

#### NotificationService.java
```java
@Service
public class NotificationService {
    public void notify(String message) {
        System.out.println("📢 Notification: " + message);
    }
}
```

#### BookRepository.java
```java
@Repository
public class BookRepository {
    private final List<Book> books = new ArrayList<>();
    
    public void save(Book book) {
        books.add(book);
    }
    
    public List<Book> findAll() {
        return new ArrayList<>(books);
    }
}
```

#### BookService.java
```java
@Service
public class BookService {
    private final BookRepository bookRepository;
    private final NotificationService notificationService;
    
    // TODO: Implement Constructor Injection
    
    public void addBook(Book book) {
        bookRepository.save(book);
        notificationService.notify("New book added: " + book.getTitle());
    }
    
    public List<Book> getAllBooks() {
        return bookRepository.findAll();
    }
}
```

#### Configuration (application.yml)
```yaml
app:
  library:
    name: City Library
    max-books: 1000
```

---

## 📝 Key Takeaways

1. ✅ Spring Boot 3 ต้องการ Java 17+ และใช้ Jakarta EE
2. ✅ ใช้ Constructor Injection เป็นหลัก
3. ✅ @Component, @Service, @Repository มีความหมายต่างกัน
4. ✅ ใช้ YAML แทน Properties เพื่อความอ่านง่าย
5. ✅ @ConfigurationProperties ดีกว่า @Value สำหรับหลาย properties

---

## 🔗 แหล่งเรียนรู้เพิ่มเติม

- [Spring Boot 3 Release Notes](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.0-Release-Notes)
- [Spring Dependency Injection](https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html)
- [Jakarta EE Migration Guide](https://jakarta.ee/)

---

## ➡️ Next: [Lesson 2 - Building REST APIs](../lesson-2/README.md)

---

**Happy Learning! 📚✨**