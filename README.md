# 📚 หลักสูตร Java 21 + Spring Boot 3 สำหรับ Junior Developer

> คอร์สเรียน Java Spring Boot 3 แบบเข้มข้น 8 ชั่วโมง สำหรับ Junior Developer ที่ต้องการพัฒนาทักษะ Backend Development

[![Java](https://img.shields.io/badge/Java-21-orange)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen)](https://spring.io/projects/spring-boot)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 🎯 เป้าหมายของคอร์ส

- เรียนรู้การพัฒนา REST API ด้วย Spring Boot 3
- เข้าใจ Spring Framework Core Concepts
- สามารถเชื่อมต่อและจัดการ Database ด้วย Spring Data JPA
- เรียนรู้ Best Practices ในการเขียน Spring Boot Application
- เตรียมพร้อมสำหรับการทำงานจริง

---

## 📋 ข้อกำหนดเบื้องต้น (Prerequisites)

- มีความรู้พื้นฐาน Java (Java 8 ขึ้นไป)
- เข้าใจ OOP Concepts
- รู้จัก Maven/Gradle พื้นฐาน
- มีความรู้เรื่อง REST API เบื้องต้น
- มี IDE ที่รองรับ (IntelliJ IDEA, Eclipse, VS Code)

---

## 📖 โครงสร้างหลักสูตร (8 ชั่วโมง)

### **ชั่วโมงที่ 1-2: Spring Boot 3 Foundation** 🏗️

#### Spring Boot 3 Overview
- ความแตกต่างระหว่าง Spring Boot 3 vs 2.x
- Jakarta EE (การเปลี่ยนจาก javax → jakarta)
- โครงสร้างโปรเจ็กต์และการ Configuration
- Spring Initializer และ Project Setup

#### Dependency Injection & IoC Container
- `@Component`, `@Service`, `@Repository`
- `@Autowired` vs Constructor Injection
- Application Properties (YAML/Properties)
- Bean Lifecycle และ Scopes

---

### **ชั่วโมงที่ 3-4: Building REST APIs** 🌐

#### REST Controllers
- `@RestController`, `@RequestMapping`
- HTTP Methods: `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`
- `@PathVariable`, `@RequestParam`, `@RequestBody`
- Response Entity และ HTTP Status Codes

#### Data Validation
- Jakarta Validation API
- `@Valid`, `@NotNull`, `@NotBlank`, `@Size`, `@Email`
- Custom Validators

#### Exception Handling
- `@ExceptionHandler`
- `@ControllerAdvice` และ Global Exception Handler
- Custom Error Responses

---

### **ชั่วโมงที่ 5-6: Database Integration** 💾

#### Spring Data JPA
- Entity Mapping (`@Entity`, `@Id`, `@GeneratedValue`)
- Relationships (`@OneToMany`, `@ManyToOne`, `@ManyToMany`)
- JpaRepository Interface
- Basic CRUD Operations
- Custom Queries (`@Query`, Named Queries)
- Pagination และ Sorting

#### Database Configuration
- H2 Database สำหรับ Development
- PostgreSQL/MySQL Configuration
- Connection Pooling
- DDL Auto Configuration

---

### **ชั่วโมงที่ 7: Testing & Security Basics** 🔒

#### Unit & Integration Testing
- JUnit 5 Fundamentals
- `@SpringBootTest`
- MockMvc สำหรับ API Testing
- `@MockBean` และ Mocking
- Test Slices (`@WebMvcTest`, `@DataJpaTest`)

#### Spring Security Basics
- Basic Authentication
- Security Configuration (`SecurityFilterChain`)
- Password Encoding
- In-Memory Authentication

---

### **ชั่วโมงที่ 8: Best Practices & Deployment** 🚀

#### Code Organization
- Layered Architecture (Controller → Service → Repository)
- DTO Pattern และ Entity Mapping
- Service Layer Best Practices
- Separation of Concerns

#### Logging & Monitoring
- SLF4J/Logback Configuration
- Log Levels และ Best Practices
- Spring Boot Actuator
- Health Checks และ Metrics

#### Deployment Basics
- Creating Executable JAR
- Docker Containerization (Basic)
- Environment-specific Configuration
- Production Ready Features

---

## 💡 เคล็ดลับสำหรับผู้สอน

1. **Hands-on เยอะๆ** 🖐️
   - ให้เขียนโปรเจ็กต์เล็กๆ ตลอดเวลา
   - ตัวอย่างเช่น Todo API, Book Management System, Employee Management

2. **Focus on Practical** 🎯
   - 8 ชั่วโมงมีเวลาไม่มาก ควรเน้นสิ่งที่ใช้งานได้จริง
   - ทฤษฎีลึกเกินไปควรเก็บไว้สำหรับคอร์สขั้นสูง

3. **Live Coding** 👨‍💻
   - Code ให้ดูแบบ Real-time พร้อมอธิบาย
   - ดีกว่าการใช้ Slides เพียงอย่างเดียว

4. **Provide Template** 📦
   - เตรียม Starter Project ไว้ให้ล่วงหน้า
   - ช่วยประหยัดเวลา Setup และ Configuration

5. **Skip Advanced Topics** ⏭️
   - เรื่องยากๆ เช่น WebFlux, Microservices, Cloud Deployment
   - ควรสอนในคอร์สต่อไป

---

## 🎓 โปรเจ็กต์ตัวอย่างที่แนะนำ

### Simple REST API Project
เลือก 1 โปรเจ็กต์เพื่อสร้างตลอดคอร์ส:

1. **Employee Management System** 👥
   - CRUD operations สำหรับพนักงาน
   - Department relationship
   - Search และ Filter

2. **Product Catalog API** 🛍️
   - Product และ Category management
   - Inventory tracking
   - Price calculations

3. **Todo/Task Management API** ✅
   - Task CRUD
   - Status management
   - User assignment

### คุณสมบัติที่ควรมีในโปรเจ็กต์:
- ✅ CRUD Operations ครบถ้วน
- ✅ Database Integration (H2)
- ✅ Data Validation
- ✅ Exception Handling
- ✅ Unit Tests พื้นฐาน
- ✅ API Documentation (Swagger/OpenAPI - Optional)

---

## 🛠️ เครื่องมือที่แนะนำ

- **IDE**: IntelliJ IDEA Community Edition / VS Code with Java Extensions
- **Build Tool**: Maven 3.9+ หรือ Gradle 8+
- **Database**: H2 (Development), PostgreSQL (Production)
- **Testing**: Postman / Insomnia / cURL
- **Version Control**: Git

---

## 📚 แหล่งเรียนรู้เพิ่มเติม

- [Spring Boot Official Documentation](https://docs.spring.io/spring-boot/docs/current/reference/html/)
- [Spring Guides](https://spring.io/guides)
- [Baeldung Spring Tutorials](https://www.baeldung.com/spring-boot)
- [Java 21 Documentation](https://docs.oracle.com/en/java/javase/21/)

---

## 🤝 การมีส่วนร่วม

ยินดีรับ Pull Requests สำหรับ:
- ✨ ตัวอย่างโค้ดเพิ่มเติม
- 📝 ปรับปรุงเนื้อหา
- 🐛 แก้ไขข้อผิดพลาด
- 💡 เพิ่มแนวทางการสอนที่ดีขึ้น

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍🏫 ผู้สอน

สร้างโดย [@atthk208](https://github.com/atthk208)

---

**Happy Coding! 💻🚀**