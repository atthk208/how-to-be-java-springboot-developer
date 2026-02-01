# 📝 แบบทดสอบ Lesson 1: Spring Boot 3 Foundation

> ทดสอบความเข้าใจหลังเรียนจบ Lesson 1

---

## ⏱️ ระยะเวลา: 15 นาที
## 📊 คะแนนเต็ม: 20 คะแนน (ข้อละ 1 คะแนน)

---

## ส่วนที่ 1: Multiple Choice (10 คะแนน)

### ข้อ 1
Spring Boot 3 ต้องการ Java version อย่างต่ำเท่าไหร่?

A. Java 8  
B. Java 11  
C. Java 17  
D. Java 21  

<details>
<summary>เฉลย</summary>

**คำตอบ: C. Java 17**

Spring Boot 3 กำหนดให้ใช้ Java 17 ขึ้นไป เป็น baseline requirement
</details>

---

### ข้อ 2
ข้อใดคือการเปลี่ยนแปลงหลักของ Spring Boot 3?

A. เปลี่ยนจาก javax.* เป็น jakarta.*  
B. ไม่รองรับ Kotlin  
C. ใช้ Spring Framework 4  
D. ไม่รองรับ Maven  

<details>
<summary>เฉลย</summary>

**คำตอบ: A. เปลี่ยนจาก javax.* เป็น jakarta.***

Spring Boot 3 อพเดทเป็น Jakarta EE ทำให้ package เปลี่ยนจาก javax เป็น jakarta
</details>

---

### ข้อ 3
Annotation ใดเหมาะสมสำหรับ Business Logic Layer?

A. @Component  
B. @Service  
C. @Repository  
D. @Controller  

<details>
<summary>เฉลย</summary>

**คำตอบ: B. @Service**

@Service ใช้สำหรับ Business Logic Layer ทำให้โค้ดอ่านเข้าใจง่ายขึ้น
</details>

---

### ข้อ 4
Dependency Injection แบบใดที่แนะนำให้ใช้มากที่สุด?

A. Field Injection  
B. Setter Injection  
C. Constructor Injection  
D. Method Injection  

<details>
<summary>เฉลย</summary>

**คำตอบ: C. Constructor Injection**

ข้อดี:
- Immutable (ใช้ final ได้)
- ทดสอบง่าย
- Null-safe
- ไม่ต้องใช้ @Autowired
</details>

---

### ข้อ 5
Bean Scope แบบ default ของ Spring คืออะไร?

A. prototype  
B. singleton  
C. request  
D. session  

<details>
<summary>เฉลย</summary>

**คำตอบ: B. singleton**

Default scope คือ singleton หมายถึง Spring Container จะสร้าง Bean เพียง instance เดียว
</details>

---

### ข้อ 6
ข้อใดถูกต้องเกี่ยวกับ @SpringBootApplication?

A. เป็นการรวม @Configuration, @EnableAutoConfiguration, @ComponentScan  
B. ใช้สำหรับ Controller เท่านั้น  
C. ต้องใส่ในทุกไฟล์  
D. ใช้แทน @Service  

<details>
<summary>เฉลย</summary>

**คำตอบ: A. เป็นการรวม @Configuration, @EnableAutoConfiguration, @ComponentScan**

@SpringBootApplication เป็น meta-annotation ที่รวม 3 annotations หลัก
</details>

---

### ข้อ 7
ไฟล์ใดที่ใช้กำหนดค่า Spring Boot Application?

A. config.xml  
B. application.properties  
C. settings.json  
D. app.config  

<details>
<summary>เฉลย</summary>

**คำตอบ: B. application.properties**

หรือใช้ application.yml ก็ได้ เป็นไฟล์ configuration หลักของ Spring Boot
</details>

---

### ข้อ 8
@PostConstruct ใช้ทำอะไร?

A. ส่ง HTTP POST Request  
B. สร้าง Bean ใหม่  
C. รันโค้ดหลังจาก Bean ถูกสร้างและ inject dependencies เสร็จ  
D. ลบ Bean  

<details>
<summary>เฉลย</summary>

**คำตอบ: C. รันโค้ดหลังจาก Bean ถูกสร้างและ inject dependencies เสร็จ**

@PostConstruct เป็น lifecycle callback ที่รันหลัง initialization เสร็จ
</details>

---

### ข้อ 9
@ConfigurationProperties เหมาะกับกรณีใด?

A. อ่าน 1 property  
B. อ่านหลาย properties ที่เกี่ยวข้องกัน  
C. สร้าง REST Controller  
D. Query Database  

<details>
<summary>เฉลย</summary>

**คำตอบ: B. อ่านหลาย properties ที่เกี่ยวข้องกัน**

@ConfigurationProperties เหมาะกับการ group properties ที่เกี่ยวข้องกันไว้ในคลาสเดียว
</details>

---

### ข้อ 10
@Repository มีประโยชน์อะไรเพิ่มจาก @Component?

A. ไม่มีประโยชน์เพิ่ม  
B. แปลง Database exceptions เป็น Spring's DataAccessException  
C. ทำให้ Query เร็วขึ้น  
D. ไม่ต้อง inject  

<details>
<summary>เฉลย</summary>

**คำตอบ: B. แปลง Database exceptions เป็น Spring's DataAccessException**

@Repository มี exception translation mechanism ทำให้จัดการ error ง่ายขึ้น
</details>

---

## ส่วนที่ 2: True/False (5 คะแนน)

### ข้อ 11
Spring Boot 3 รองรับ Java 8

- [ ] ถูก
- [ ] ผิด

<details>
<summary>เฉลย</summary>

**ผิด** - Spring Boot 3 ต้องการ Java 17 ขึ้นไป
</details>

---

### ข้อ 12
Field Injection เป็นวิธีที่แนะนำในการทำ Dependency Injection

- [ ] ถูก
- [ ] ผิด

<details>
<summary>เฉลย</summary>

**ผิด** - Constructor Injection เป็นวิธีที่แนะนำ
</details>

---

### ข้อ 13
application.yml และ application.properties ทำงานเหมือนกัน

- [ ] ถูก
- [ ] ผิด

<details>
<summary>เฉลย</summary>

**ถูก** - ทั้งสองทำงานเหมือนกัน แต่ YAML อ่านง่ายกว่า
</details>

---

### ข้อ 14
@PreDestroy รันก่อนที่ Bean จะถูกสร้าง

- [ ] ถูก
- [ ] ผิด

<details>
<summary>เฉลย</summary>

**ผิด** - @PreDestroy รันก่อนที่ Bean จะถูกทำลาย ไม่ใช่ก่อนสร้าง
</details>

---

### ข้อ 15
Spring Boot ใช้ IoC (Inversion of Control) pattern

- [ ] ถูก
- [ ] ผิด

<details>
<summary>เฉลย</summary>

**ถูก** - Spring Boot ใช้ IoC Container ในการจัดการ Bean lifecycle
</details>

---

## ส่วนที่ 3: Code Review (5 คะแนน)

### ข้อ 16-17: จงหาข้อผิดพลาดในโค้ดต่อไปนี้

```java
@Service
public class UserService {
    @Autowired
    private UserRepository userRepository;
    
    @Autowired
    private EmailService emailService;
    
    public void createUser(String name) {
        User user = new User(name);
        userRepository.save(user);
        emailService.send("Welcome!");
    }
}
```

**ข้อ 16:** ควรใช้ Injection แบบใดแทน?

<details>
<summary>เฉลย</summary>

**ควรใช้ Constructor Injection**

```java
@Service
public class UserService {
    private final UserRepository userRepository;
    private final EmailService emailService;
    
    public UserService(UserRepository userRepository, 
                      EmailService emailService) {
        this.userRepository = userRepository;
        this.emailService = emailService;
    }
    
    public void createUser(String name) {
        User user = new User(name);
        userRepository.save(user);
        emailService.send("Welcome!");
    }
}
```
</details>

---

**ข้อ 17:** ข้อดีของการแก้ไขคืออะไร?

<details>
<summary>เฉลย</summary>

**ข้อดี:**
1. Immutable - ใช้ final ได้
2. Null-safe - ไม่มีทาง null
3. ทดสอบง่าย - inject mock ได้ง่าย
4. ไม่ต้องใช้ @Autowired (Spring 4.3+)
5. Dependencies ชัดเจน
</details>

---

### ข้อ 18-19: Configuration Properties

```java
// application.yml
app:
  name: MyApp
  version: 1.0.0
  settings:
    max-users: 100
    timeout: 30
```

**ข้อ 18:** เขียน @ConfigurationProperties class ที่ถูกต้อง

<details>
<summary>เฉลย</summary>

```java
@Configuration
@ConfigurationProperties(prefix = "app")
public class AppProperties {
    private String name;
    private String version;
    private Settings settings;
    
    // Getters and Setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    
    public String getVersion() { return version; }
    public void setVersion(String version) { this.version = version; }
    
    public Settings getSettings() { return settings; }
    public void setSettings(Settings settings) { this.settings = settings; }
    
    public static class Settings {
        private int maxUsers;
        private int timeout;
        
        public int getMaxUsers() { return maxUsers; }
        public void setMaxUsers(int maxUsers) { this.maxUsers = maxUsers; }
        
        public int getTimeout() { return timeout; }
        public void setTimeout(int timeout) { this.timeout = timeout; }
    }
}
```
</details>

---

**ข้อ 19:** ถ้าต้องการอ่านเฉพาะ app.name ใช้วิธีไหนง่ายที่สุด?

<details>
<summary>เฉลย</summary>

**ใช้ @Value**

```java
@Service
public class MyService {
    @Value("${app.name}")
    private String appName;
}
```

หรือ

```java
@Service
public class MyService {
    private final String appName;
    
    public MyService(@Value("${app.name}") String appName) {
        this.appName = appName;
    }
}
```
</details>

---

### ข้อ 20: Lifecycle

โค้ดต่อไปนี้จะ print อะไรออกมา ตามลำดับ?

```java
@Component
public class MyBean {
    public MyBean() {
        System.out.println("1. Constructor");
    }
    
    @PostConstruct
    public void init() {
        System.out.println("2. PostConstruct");
    }
    
    @PreDestroy
    public void cleanup() {
        System.out.println("3. PreDestroy");
    }
}
```

<details>
<summary>เฉลย</summary>

**เมื่อ Application เริ่มต้น:**
```
1. Constructor
2. PostConstruct
```

**เมื่อ Application ปิด:**
```
3. PreDestroy
```

**ลำดับ Lifecycle:**
1. Constructor ถูกเรียก
2. Dependencies ถูก inject
3. @PostConstruct ถูกเรียก
4. Bean พร้อมใช้งาน
5. @PreDestroy ถูกเรียกก่อน destroy
</details>

---

## 🎯 เกณฑ์การผ่าน

- **18-20 คะแนน**: ممتاز (Excellent) 🌟
- **15-17 คะแนน**: ดีมาก (Very Good) ⭐
- **12-14 คะแนน**: ดี (Good) ✅
- **ต่ำกว่า 12 คะแนน**: ควรทบทวนอีกครั้ง 📚

---

## 📖 หากไม่ผ่าน

ให้ทบทวนเนื้อหาในหัวข้อ:
- [ ] Spring Boot 3 Overview
- [ ] Jakarta EE Migration
- [ ] Dependency Injection Patterns
- [ ] Bean Lifecycle
- [ ] Configuration Properties

---

## ✅ เมื่อผ่านแล้ว

พร้อมไปต่อที่ ➡️ [Lesson 2 - Building REST APIs](../lesson-2/README.md)

---

**Good Luck! 🍀**