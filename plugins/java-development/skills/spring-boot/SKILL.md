---
name: spring-boot
description: Master Spring Boot with auto-configuration, REST APIs, JPA, security, testing, and production-ready features for enterprise applications.
---

# Spring Boot Development

Build production-ready Spring Boot applications with REST APIs, data access, security, and microservices patterns.

## Core Patterns

### REST Controller
```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    @Autowired
    private UserService userService;

    @GetMapping
    public List<User> getAllUsers() {
        return userService.findAll();
    }

    @GetMapping("/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        return userService.findById(id)
            .map(ResponseEntity::ok)
            .orElse(ResponseEntity.notFound().build());
    }

    @PostMapping
    public ResponseEntity<User> createUser(@Valid @RequestBody UserDto userDto) {
        User user = userService.create(userDto);
        return ResponseEntity.status(HttpStatus.CREATED).body(user);
    }
}
```

### Service Layer
```java
@Service
@Transactional
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public List<User> findAll() {
        return userRepository.findAll();
    }

    public Optional<User> findById(Long id) {
        return userRepository.findById(id);
    }

    public User create(UserDto dto) {
        User user = new User();
        user.setName(dto.getName());
        user.setEmail(dto.getEmail());
        return userRepository.save(user);
    }
}
```

### Repository
```java
@Repository
public interface UserRepository extends JpaRepository<User, Long> {
    Optional<User> findByEmail(String email);
    List<User> findByNameContaining(String name);
}
```

### Configuration
```java
@Configuration
public class AppConfig {

    @Bean
    public ModelMapper modelMapper() {
        return new ModelMapper();
    }

    @Bean
    public RestTemplate restTemplate() {
        return new RestTemplate();
    }
}
```

## Best Practices

1. Use constructor injection
2. Implement proper exception handling
3. Use DTOs for API contracts
4. Leverage Spring Boot starters
5. Use profiles for environments
6. Implement proper logging
7. Write integration tests
8. Use validation annotations

## Resources
- https://spring.io/projects/spring-boot
- https://spring.io/guides
