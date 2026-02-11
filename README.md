# Proyecto: ICC-PPW Frameworks Backend Fundamentos

## Estructura del Proyecto

El proyecto tiene la siguiente estructura de directorios y archivos:

```
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── ec/
│   │   │       └── edu/
│   │   │           └── ups/
│   │   │               └── icc/
│   │   │                   └── fundamentos01/
│   │   │                       ├── Fundamentos01Application.java
│   │   │                       ├── categories/
│   │   │                       │   ├── controller/
│   │   │                       │   │   └── CategoryController.java
│   │   │                       │   ├── dtos/
│   │   │                       │   │   ├── CategoryCreateDto.java
│   │   │                       │   │   └── CategoryResponseDto.java
│   │   │                       │   ├── entity/
│   │   │                       │   │   ├── Categoria.java
│   │   │                       │   │   └── CategoryEntity.java
│   │   │                       │   ├── mappers/
│   │   │                       │   │   └── CategoryMapper.java
│   │   │                       │   └── reporitory/
│   │   │                       │       └── CategoryRepository.java
│   │   │                       │   └── service/
│   │   │                       │       ├── CategoryService.java
│   │   │                       │       └── CategoryServiceImpl.java
│   │   │                       ├── core/
│   │   │                       │   ├── controllers/
│   │   │                       │   │   └── StatusController.java
│   │   │                       │   └── entities/
│   │   │                       │       └── BaseModel.java
│   │   │                       ├── exceptions/
│   │   │                       │   ├── base/
│   │   │                       │   │   └── ApplicationException.java
│   │   │                       │   ├── domain/
│   │   │                       │   │   ├── BadRequestException.java
│   │   │                       │   │   ├── BusinessException.java
│   │   │                       │   │   ├── ConflictException.java
│   │   │                       │   │   └── NotFoundException.java
│   │   │                       │   ├── handler/
│   │   │                       │   │   └── GlobalExceptionHandler.java
│   │   │                       │   └── response/
│   │   │                       │       └── ErrorResponse.java
│   │   │                       ├── products/
│   │   │                       │   ├── controllers/
│   │   │                       │   │   └── ProductController.java
│   │   │                       │   ├── dtos/
│   │   │                       │   │   ├── CreateProductDto.java
│   │   │                       │   │   ├── PartialUpdateProductDto.java
│   │   │                       │   │   ├── ProductResponseDto.java
│   │   │                       │   │   ├── SecureUpdateProductDto.java
│   │   │                       │   │   ├── UpdateProductDto.java
│   │   │                       │   │   └── ValidateProductNameDto.java
│   │   │                       │   ├── mappers/
│   │   │                       │   │   └── ProductMapper.java
│   │   │                       │   ├── models/
│   │   │                       │   │   ├── Product.java
│   │   │                       │   │   └── ProductEntity.java
│   │   │                       │   ├── repository/
│   │   │                       │   │   └── ProductRepository.java
│   │   │                       │   └── services/
│   │   │                       │       ├── ProductService.java
│   │   │                       │       └── ProductServiceImpl.java
│   │   │                       ├── security/
│   │   │                       │   ├── config/
│   │   │                       │   │   ├── JacksonConfig.java
│   │   │                       │   │   ├── JwtProperties.java
│   │   │                       │   │   └── SecurityConfig.java
│   │   │                       │   ├── controllers/
│   │   │                       │   │   └── AuthController.java
│   │   │                       │   ├── dtos/
|   |   |                       |   |   ├── AuthResponseDto.java
│   │   │                       │   │   ├── LoginRequestDto.java
│   │   │                       │   │   └── RegiterRequestDto.java
│   │   │                       │   ├── filters/
|   |   |                       |   |   ├── JwtAuthenticationEntryPoint.java
│   │   │                       │   │   └── JwtAuthenticationFilter.java
│   │   │                       │   ├── init/
│   │   │                       │   │   └── DataInitializer.java
│   │   │                       │   ├── models/
|   |   |                       |   |   ├── RoleEntity.java
│   │   │                       │   │   └── RoleName.java
│   │   │                       │   ├── repository/
│   │   │                       │   │   └── RolesRepository.java
│   │   │                       │   ├── service/
|   |   |                       |   |   ├── AuthService.java
│   │   │                       │   │   ├── UserDetailsImpl.java
│   │   │                       │   │   └── UserDetailsServiceImpl.java
│   │   │                       │   └── utils/
│   │   │                       │   │   └── JwtUtil.java
│   │   │                       └── users/
│   │   │                           ├── controllers/
│   │   │                           │   └── UserController.java
│   │   │                           ├── dtos/
|   |   |                           |   ├── CreateUserDto.java
│   │   │                           │   ├── PartialUpdateUserDto.java
│   │   │                           │   ├── UpdateUserDto.java
│   │   │                           │   └── UserResposeDto.java
│   │   │                           ├── mappers/
│   │   │                           │   └── UserMapper.java
│   │   │                           ├── models/
│   │   │                           │   ├── User.java
│   │   │                           │   └── UserEntity.java
│   │   │                           ├── repository/
│   │   │                           │   └── UserRepository.java
│   │   │                           └── services/
│   │   │                           │   ├── UserService.java
│   │   │                           │   └── UserServciceImpl.java
│   └── resources/
│       └── application.yaml

```

## Código de las Clases

A continuación, se incluye el código de cada clase del proyecto:

### Fundamentos01Application.java
```java
package ec.edu.ups.icc.fundamentos01;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Fundamentos01Application {

	public static void main(String[] args) {
		SpringApplication.run(Fundamentos01Application.class, args);
	}

}

```
### CategoryController.java
```java
package ec.edu.ups.icc.fundamentos01.categories.controller;

import org.springframework.web.bind.annotation.RestController;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryCreateDto;
import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;
import ec.edu.ups.icc.fundamentos01.categories.service.CategoryService;

import java.util.List;

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.GetMapping;

@RestController
@RequestMapping("/api/categories")
public class CategoryController {

    private CategoryService categoryService;

    public CategoryController(CategoryService categoryService) {
        this.categoryService = categoryService;

    }

    // @PostMapping()
    // public ResponseEntity<String> create(@RequestBody CategoryCreateDto entity) {

    // categoryService.save(entity);
    // return ResponseEntity.ok("Categoría creada exitosamente");
    // }

    @PostMapping
    public ResponseEntity<CategoryResponseDto> create(@RequestBody CategoryCreateDto entity) {

        CategoryResponseDto response = categoryService.save(entity);

        return ResponseEntity.status(HttpStatus.CREATED).body(response);
    }

    @GetMapping()
    public ResponseEntity<List<CategoryResponseDto>> getAll() {

        return ResponseEntity.ok(categoryService.findAll());
    }

}
```

### CategoryCreateDto.java
```java
package ec.edu.ups.icc.fundamentos01.categories.dtos;

public class CategoryCreateDto {

    public String name;

    public String description;

}
```

### CategoryResponseDto.java
```java
package ec.edu.ups.icc.fundamentos01.categories.dtos;

public class CategoryResponseDto {
    public Long id;
    public String name;
    public String description;

}
```

### Categoria.java
```java
package ec.edu.ups.icc.fundamentos01.categories.entity;

public class Categoria {

    private Long id;
    private String name;
    private String description;

    public Categoria() {
    }

    public Categoria(Long id, String name, String description) {
        this.id = id;
        this.name = name;
        this.description = description;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

}
```

### CategoryEntity.java
```java
package ec.edu.ups.icc.fundamentos01.categories.entity;

import java.util.HashSet;
import java.util.Set;

import ec.edu.ups.icc.fundamentos01.core.entities.BaseModel;
import ec.edu.ups.icc.fundamentos01.products.models.ProductEntity;
import jakarta.persistence.Column;
import jakarta.persistence.Entity;
import jakarta.persistence.FetchType;
import jakarta.persistence.ManyToMany;
import jakarta.persistence.Table;

@Entity
@Table(name = "categories")
public class CategoryEntity extends BaseModel {

    @Column(nullable = false, unique = true, length = 120)
    private String name;

    @Column(length = 500)
    private String description;

    @ManyToMany(mappedBy = "categories", fetch = FetchType.LAZY)
    private Set<ProductEntity> products = new HashSet<>();

    // Getters y setters
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public Set<ProductEntity> getProducts() {
        return products;
    }

    public void setProducts(Set<ProductEntity> products) {
        this.products = products;
    }

}```

### CategoryMapper.java
```java
package ec.edu.ups.icc.fundamentos01.categories.mappers;

import java.util.ArrayList;
import java.util.List;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;
import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;
import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;

public class CategoryMapper {

    public static CategoryResponseDto toResponseDto(CategoryEntity categoryEntity

    ) {
        List<ProductResponseDto> productsDTO = new ArrayList<>();
        for (var productEntity : categoryEntity.getProducts()) {
            var productDto = new ProductResponseDto();
            productDto.id = productEntity.getId();
            productDto.name = productEntity.getName();
            productDto.description = productEntity.getDescription();
            productDto.price = productEntity.getPrice();
            productsDTO.add(productDto);
        }
        return new CategoryResponseDto() {

            {
                id = categoryEntity.getId();
                name = categoryEntity.getName();
                description = categoryEntity.getDescription();
                // products = productsDTO;

            }
        };

    }

}
```

### CategoryRepository.java
```java
package ec.edu.ups.icc.fundamentos01.categories.reporitory;

import java.util.Optional;

import org.springframework.data.jpa.repository.JpaRepository;

import org.springframework.stereotype.Repository;

import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;

@Repository
public interface CategoryRepository extends JpaRepository<CategoryEntity, Long> {

        /**
         * Verifica si ya existe una categoría con ese nombre
         * Útil para validaciones de unicidad
         */
        boolean existsByName(String name);

        /**
         * Busca categoría por nombre (case insensitive)
         */
        Optional<CategoryEntity> findByNameIgnoreCase(String name);

}
```

### CategoryService.java
```java
package ec.edu.ups.icc.fundamentos01.categories.service;

import java.util.List;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryCreateDto;
import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;

public interface CategoryService {

    List<CategoryResponseDto> findAll();

    CategoryResponseDto save(CategoryCreateDto createDto);

}
```

### CategoryServiceImpl.java
```java
package ec.edu.ups.icc.fundamentos01.categories.service;

import java.util.List;

import org.springframework.stereotype.Service;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryCreateDto;
import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;
import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;
import ec.edu.ups.icc.fundamentos01.categories.mappers.CategoryMapper;
import ec.edu.ups.icc.fundamentos01.categories.reporitory.CategoryRepository;

@Service
public class CategoryServiceImpl implements CategoryService {

    private CategoryRepository categoryRepository;

    public CategoryServiceImpl(CategoryRepository categoryRepository) {
        this.categoryRepository = categoryRepository;
    }

    @Override
    public List<CategoryResponseDto> findAll() {
        return categoryRepository.findAll().stream().map(CategoryMapper::toResponseDto).toList();
    }

    @Override
    public CategoryResponseDto save(CategoryCreateDto createDto) {

        var categoryEntity = new CategoryEntity();
        categoryEntity.setName(createDto.name);
        categoryEntity.setDescription(createDto.description);
        categoryRepository.save(categoryEntity);

        return CategoryMapper.toResponseDto(categoryEntity);
    }

}
```

### StatusController.java
```java
package ec.edu.ups.icc.fundamentos01.core.controllers;

import org.springframework.web.bind.annotation.RestController;

import java.time.LocalDateTime;
import java.util.Map;

import org.springframework.web.bind.annotation.GetMapping;

@RestController
public class StatusController {

    @GetMapping("/api/status")
    public Map<String, Object> status() {
        return Map.of(
                "service", "Spring Boot API",
                "status", "running",
                "timestamp", LocalDateTime.now().toString());
    }

}
```

### BaseModel.java
```java
package ec.edu.ups.icc.fundamentos01.core.entities;

import java.time.LocalDateTime;
import jakarta.persistence.*;

@MappedSuperclass
public abstract class BaseModel {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private LocalDateTime createdAt;
    private LocalDateTime updatedAt;
    private boolean deleted;

    @PrePersist
    protected void onCreate() {
        this.deleted = false;
        this.createdAt = LocalDateTime.now();
    }

    @PreUpdate
    protected void onUpdate() {
        this.updatedAt = LocalDateTime.now();
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public LocalDateTime getCreatedAt() {
        return createdAt;
    }

    public LocalDateTime getUpdatedAt() {
        return updatedAt;
    }

    public boolean isDeleted() {
        return deleted;
    }
}
```

### ApplicationException.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.base;

import org.springframework.http.HttpStatus;

public abstract class ApplicationException extends RuntimeException {

    private final HttpStatus status;

    protected ApplicationException(HttpStatus status, String message) {
        super(message);
        this.status = status;
    }

    public HttpStatus getStatus() {
        return status;
    }

    
}
```

### BadRequestException.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.domain;

import org.springframework.http.HttpStatus;

import ec.edu.ups.icc.fundamentos01.exceptions.base.ApplicationException;

public class BadRequestException extends ApplicationException {

    public BadRequestException(String message) {
        super(HttpStatus.BAD_REQUEST, message);
    }
}```

### BusinessException.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.domain;

import org.springframework.http.HttpStatus;

import ec.edu.ups.icc.fundamentos01.exceptions.base.ApplicationException;

public class BusinessException extends ApplicationException {

    public BusinessException(String message) {
        super(HttpStatus.UNPROCESSABLE_CONTENT, message);
    }

    protected BusinessException(HttpStatus status, String message) {
        super(status, message);
    }
}```

### ConflictException.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.domain;

import org.springframework.http.HttpStatus;

import ec.edu.ups.icc.fundamentos01.exceptions.base.ApplicationException;

public class ConflictException extends ApplicationException {

    public ConflictException(String message) {
        super(HttpStatus.CONFLICT, message);
    }
}```

### NotFoundException.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.domain;

import org.springframework.http.HttpStatus;

import ec.edu.ups.icc.fundamentos01.exceptions.base.ApplicationException;

public class NotFoundException extends ApplicationException {

    public NotFoundException(String message) {
        super(HttpStatus.NOT_FOUND, message);
    }
}```

### GlobalExceptionHandler.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.handler;

import java.util.HashMap;
import java.util.Map;

import javax.security.sasl.AuthenticationException;

import jakarta.servlet.http.HttpServletRequest;

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.security.access.AccessDeniedException;
import org.springframework.security.authorization.AuthorizationDeniedException;
import org.springframework.web.bind.MethodArgumentNotValidException;

import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.RestControllerAdvice;

import ec.edu.ups.icc.fundamentos01.exceptions.base.ApplicationException;
import ec.edu.ups.icc.fundamentos01.exceptions.response.ErrorResponse;

@RestControllerAdvice
public class GlobalExceptionHandler {

        @ExceptionHandler(ApplicationException.class)
        public ResponseEntity<ErrorResponse> handleApplicationException(
                        ApplicationException ex,
                        HttpServletRequest request) {
                ErrorResponse response = new ErrorResponse(
                                ex.getStatus(),
                                ex.getMessage(),
                                request.getRequestURI());

                return ResponseEntity
                                .status(ex.getStatus())
                                .body(response);
        }

        @ExceptionHandler(MethodArgumentNotValidException.class)
        public ResponseEntity<ErrorResponse> handleValidationException(
                        MethodArgumentNotValidException ex,
                        HttpServletRequest request) {
                Map<String, String> errors = new HashMap<>();

                ex.getBindingResult()
                                .getFieldErrors()
                                .forEach(error -> errors.put(error.getField(), error.getDefaultMessage()));

                ErrorResponse response = new ErrorResponse(
                                HttpStatus.BAD_REQUEST,
                                "Datos de entrada inválidos",
                                request.getRequestURI(),
                                errors);

                return ResponseEntity
                                .badRequest()
                                .body(response);
        }
        // ============== EXCEPCIONES DE SEGURIDAD ==============

        /**
         * Maneja AuthorizationDeniedException (Spring Security 6.x)
         * Se lanza cuando un usuario autenticado no tiene los permisos necesarios
         * 
         * Contexto: Ocurre cuando @PreAuthorize evalúa a false
         * Ejemplo: Usuario con ROLE_USER intenta acceder a endpoint con
         * hasRole('ADMIN')
         */
        @ExceptionHandler(AuthorizationDeniedException.class)
        public ResponseEntity<ErrorResponse> handleAuthorizationDeniedException(
                        AuthorizationDeniedException ex,
                        HttpServletRequest request) {
                ErrorResponse response = new ErrorResponse(
                                HttpStatus.FORBIDDEN,
                                "No tienes permisos para acceder a este recurso",
                                request.getRequestURI());

                return ResponseEntity
                                .status(HttpStatus.FORBIDDEN)
                                .body(response);
        }

        /**
         * Maneja AccessDeniedException (Spring Security legacy)
         * Fallback para versiones anteriores de Spring Security o casos específicos
         * 
         * Contexto: Excepción estándar de acceso denegado
         * También se lanza desde código personalizado de validación de ownership
         */
        @ExceptionHandler(AccessDeniedException.class)
        public ResponseEntity<ErrorResponse> handleAccessDeniedException(
                        AccessDeniedException ex,
                        HttpServletRequest request) {
                ErrorResponse response = new ErrorResponse(
                                HttpStatus.FORBIDDEN,
                                "Acceso denegado. No tienes los permisos necesarios",
                                request.getRequestURI());

                return ResponseEntity
                                .status(HttpStatus.FORBIDDEN)
                                .body(response);
        }

        /**
         * Maneja AuthenticationException
         * Se lanza cuando hay problemas con la autenticación
         * 
         * Contexto: Problemas con credenciales, tokens inválidos, sesión expirada
         * Nota: JwtAuthenticationFilter ya maneja la mayoría de casos de tokens
         * inválidos
         */
        @ExceptionHandler(AuthenticationException.class)
        public ResponseEntity<ErrorResponse> handleAuthenticationException(
                        AuthenticationException ex,
                        HttpServletRequest request) {
                ErrorResponse response = new ErrorResponse(
                                HttpStatus.UNAUTHORIZED,
                                "Credenciales inválidas o sesión expirada",
                                request.getRequestURI());

                return ResponseEntity
                                .status(HttpStatus.UNAUTHORIZED)
                                .body(response);
        }

        // ============== EXCEPCIONES GENERALES ==============

        /**
         * Maneja cualquier excepción no capturada por otros manejadores
         * Debe ser el último manejador (más genérico)
         */

        @ExceptionHandler(Exception.class)
        public ResponseEntity<ErrorResponse> handleUnexpectedException(
                        Exception ex,
                        HttpServletRequest request) {
                ErrorResponse response = new ErrorResponse(
                                HttpStatus.INTERNAL_SERVER_ERROR,
                                "Error interno del servidor",
                                request.getRequestURI());

                return ResponseEntity
                                .status(HttpStatus.INTERNAL_SERVER_ERROR)
                                .body(response);
        }
}```

### ErrorResponse.java
```java
package ec.edu.ups.icc.fundamentos01.exceptions.response;

import java.io.Serializable;
import java.time.LocalDateTime;
import java.util.Map;

import org.springframework.http.HttpStatus;

import com.fasterxml.jackson.annotation.JsonInclude;

@JsonInclude(JsonInclude.Include.NON_NULL)
public class ErrorResponse implements Serializable {

    private LocalDateTime timestamp;
    private int status;
    private String error;
    private String message;
    private String path;
    private Map<String, String> details;

    public ErrorResponse(
            HttpStatus status,
            String message,
            String path,
            Map<String, String> details
    ) {
        this.timestamp = LocalDateTime.now();
        this.status = status.value();
        this.error = status.getReasonPhrase();
        this.message = message;
        this.path = path;
        this.details = details;
    }

    public ErrorResponse(HttpStatus status, String message, String path) {
        this(status, message, path, null);
    }

    public LocalDateTime getTimestamp() {
        return timestamp;
    }

    public int getStatus() {
        return status;
    }

    public String getError() {
        return error;
    }

    public String getMessage() {
        return message;
    }

    public String getPath() {
        return path;
    }

    public Map<String, String> getDetails() {
        return details;
    }

    
}```

### ProductController.java
```java
package ec.edu.ups.icc.fundamentos01.products.controllers;

import java.util.List;

import org.springframework.data.domain.Page;
import org.springframework.data.domain.Slice;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.security.access.prepost.PreAuthorize;
import org.springframework.security.core.annotation.AuthenticationPrincipal;
import org.springframework.web.bind.annotation.DeleteMapping;
import org.springframework.web.bind.annotation.GetMapping;

import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.PutMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

import ec.edu.ups.icc.fundamentos01.products.dtos.CreateProductDto;

import ec.edu.ups.icc.fundamentos01.products.dtos.UpdateProductDto;

import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;

import ec.edu.ups.icc.fundamentos01.products.services.ProductService;
import ec.edu.ups.icc.fundamentos01.security.service.UserDetailsImpl;
import jakarta.validation.Valid;

@RestController
@RequestMapping("/api/products")
public class ProductController {

    private final ProductService productService;

    public ProductController(ProductService productService) {
        this.productService = productService;
    }

    /**
     * Lista todos los productos con paginación
     * Ejemplo: GET /api/products?page=0&size=10&sort=name,asc
     */
    @GetMapping("/paginado")
    public ResponseEntity<Page<ProductResponseDto>> findAll(
            @RequestParam(defaultValue = "0") int page,
            @RequestParam(defaultValue = "10") int size,
            @RequestParam(defaultValue = "id") String[] sort) {

        Page<ProductResponseDto> products = productService.findAllPaginado(page, size, sort);
        return ResponseEntity.ok(products);
    }

    // ============== PAGINACIÓN CON SLICE (PERFORMANCE) ==============

    /**
     * Lista productos usando Slice para mejor performance
     * Ejemplo: GET /api/products/slice?page=0&size=10&sort=createdAt,desc
     */
    @GetMapping("/slice")
    public ResponseEntity<Slice<ProductResponseDto>> findAllSlice(
            @RequestParam(defaultValue = "0") int page,
            @RequestParam(defaultValue = "10") int size,
            @RequestParam(defaultValue = "id") String[] sort) {

        Slice<ProductResponseDto> products = productService.findAllSlice(page, size, sort);
        return ResponseEntity.ok(products);
    }

    // ============== PAGINACIÓN CON FILTROS (CONTINUANDO TEMA 09) ==============

    /**
     * Lista productos con filtros y paginación
     * Ejemplo: GET /api/products/search?name=laptop&minPrice=500&page=0&size=5
     */
    @GetMapping("/search")
    public ResponseEntity<Page<ProductResponseDto>> findWithFilters(
            @RequestParam(required = false) String name,
            @RequestParam(required = false) Double minPrice,
            @RequestParam(required = false) Double maxPrice,
            @RequestParam(required = false) Long categoryId,
            @RequestParam(defaultValue = "0") int page,
            @RequestParam(defaultValue = "10") int size,
            @RequestParam(defaultValue = "createdAt") String[] sort) {

        Page<ProductResponseDto> products = productService.findWithFilters(
                name, minPrice, maxPrice, categoryId, page, size, sort);

        return ResponseEntity.ok(products);
    }

    // ============== USUARIOS CON SUS PRODUCTOS PAGINADOS ==============

    /**
     * Productos de un usuario específico con paginación
     * Ejemplo: GET /api/products/user/1?page=0&size=5&sort=price,desc
     */
    @GetMapping("/userProduct/{userId}")
    public ResponseEntity<Page<ProductResponseDto>> findByUserId(
            @PathVariable Long userId,
            @RequestParam(required = false) String name,
            @RequestParam(required = false) Double minPrice,
            @RequestParam(required = false) Double maxPrice,
            @RequestParam(required = false) Long categoryId,
            @RequestParam(defaultValue = "0") int page,
            @RequestParam(defaultValue = "10") int size,
            @RequestParam(defaultValue = "createdAt") String[] sort) {

        Page<ProductResponseDto> products = productService.findByUserIdWithFilters(
                userId, name, minPrice, maxPrice, categoryId, page, size, sort);

        return ResponseEntity.ok(products);
    }

    @PostMapping
    public ResponseEntity<ProductResponseDto> create(@Valid @RequestBody
    CreateProductDto dto) {
    ProductResponseDto created = productService.create(dto);
    return ResponseEntity.status(HttpStatus.CREATED).body(created);
    }


    @GetMapping
    @PreAuthorize("hasRole('ADMIN')")
    public ResponseEntity<List<ProductResponseDto>> findAll() {
        List<ProductResponseDto> products = productService.findAll();
        return ResponseEntity.ok(products);
    }

    @GetMapping("/{id}")
    public ResponseEntity<ProductResponseDto> findById(@PathVariable("id") String id) {
        ProductResponseDto product = productService.findById(Long.parseLong(id));
        return ResponseEntity.ok(product);
    }

    @GetMapping("/user/{userId}")
    public ResponseEntity<List<ProductResponseDto>> findByUserId(@PathVariable("userId") Long userId) {
        List<ProductResponseDto> products = productService.findByUserId(userId);
        return ResponseEntity.ok(products);
    }

    @GetMapping("/category/{categoryId}")
    public ResponseEntity<List<ProductResponseDto>> findByCategoryId(@PathVariable("categoryId") Long categoryId) {
        List<ProductResponseDto> products = productService.findByCategoryId(categoryId);
        return ResponseEntity.ok(products);
    }

    // @PutMapping("/{id}")
    // public ResponseEntity<ProductResponseDto> update(
    //         @PathVariable("id") Long id,
    //         @Valid @RequestBody UpdateProductDto dto) {
    //     ProductResponseDto updated = productService.update(id, dto);
    //     return ResponseEntity.ok(updated);
    // }

    // @DeleteMapping("/{id}")
    // public ResponseEntity<Void> delete(@PathVariable("id") Long id) {
    //     productService.delete(id);
    //     return ResponseEntity.noContent().build();
    // }
    /**
     * Actualizar producto (solo dueño, ADMIN o MODERATOR)
     * 
     * El usuario autenticado se extrae del JWT mediante @AuthenticationPrincipal
     * y se pasa al servicio para validar ownership
     */
    @PutMapping("/{id}")
    public ResponseEntity<ProductResponseDto> update(
            @PathVariable Long id,
            @Valid @RequestBody UpdateProductDto dto,
            @AuthenticationPrincipal UserDetailsImpl currentUser) {  // ← Usuario del JWT
        
        ProductResponseDto updated = productService.update(id, dto, currentUser);
        return ResponseEntity.ok(updated);
    }

    /**
     * Eliminar producto (solo dueño, ADMIN o MODERATOR)
     * 
     * El usuario autenticado se extrae del JWT mediante @AuthenticationPrincipal
     * y se pasa al servicio para validar ownership
     */
    @DeleteMapping("/{id}")
    public ResponseEntity<Void> delete(
            @PathVariable Long id,
            @AuthenticationPrincipal UserDetailsImpl currentUser) {  // ← Usuario del JWT
        
        productService.delete(id, currentUser);
        return ResponseEntity.noContent().build();
    }
```

### CreateProductDto.java
```java
package ec.edu.ups.icc.fundamentos01.products.dtos;

import java.util.Set;

import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Positive;
import jakarta.validation.constraints.Size;

public class CreateProductDto {
    @NotBlank(message = "El nombre es obligatorio")
    @Size(min = 3, max = 150, message = "El nombre debe tener entre 3 y 150 caracteres")
    public String name;

    @NotNull(message = "El precio es obligatorio")
    @Positive(message = "El precio debe ser mayor a 0")
    public Double price;

    @Size(max = 500, message = "La descripción no puede exceder los 500 caracteres")
    public String description;

    // ============== RELACIONES ==============

    @NotNull(message = "El ID del usuario es obligatorio")
    public Long userId;

    // @NotNull(message = "El ID de la categoría es obligatorio")
    // public Long categoryId;

    @NotNull(message = "Debe especificar al menos una categoría")
    @Size(min = 1, message = "El producto debe tener al menos una categoría")
    public Set<Long> categoryIds; // Múltiples categorías

}
```

### PartialUpdateProductDto.java
```java
package ec.edu.ups.icc.fundamentos01.products.dtos;

import java.util.Set;

import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Positive;
import jakarta.validation.constraints.Size;

public class PartialUpdateProductDto {

    @Size(min = 3, max = 150)
    public String name;

    @Positive
    public Double price;

    @Size(max = 500)
    public String description;

    @NotNull(message = "Debe especificar al menos una categoría")
    @Size(min = 1, message = "El producto debe tener al menos una categoría")
    public Set<Long> categoryIds; // Múltiples categorías

}
```

### ProductResponseDto.java
```java
package ec.edu.ups.icc.fundamentos01.products.dtos;

import java.time.LocalDateTime;
import java.util.List;

import com.fasterxml.jackson.annotation.JsonPropertyOrder;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;

@JsonPropertyOrder({
        "id",
        "name",
        "price",
        "description",
        "user",
        "categories",
        "createdAt",
        "updatedAt"
})
public class ProductResponseDto {
    public Long id;
    public String name;
    public Double price;
    public String description;

    // ============== OBJETOS ANIDADOS ==============

    public UserSummaryDto user;

    // public CategoryResponseDto category;
    // ============== CATEGORÍAS (N:N) - Lista de objetos ==============
    public List<CategoryResponseDto> categories;

    // ============== AUDITORÍA ==============

    public LocalDateTime createdAt;
    public LocalDateTime updatedAt;

    // ============== DTOs INTERNOS ==============

    public static class UserSummaryDto {
        public Long id;
        public String name;
        public String email;
    }

}
```

### SecureUpdateProductDto.java
```java
package ec.edu.ups.icc.fundamentos01.products.dtos;

import java.util.Set;

import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Size;

public class SecureUpdateProductDto {

    public String name;
    public Double price;
    public String description;
    public String reason;

    // ============== RELACIONES ==============

    @NotNull(message = "El ID del usuario es obligatorio")
    public Long userId;

    // @NotNull(message = "El ID de la categoría es obligatorio")
    // public Long categoryId;

    @NotNull(message = "Debe especificar al menos una categoría")
    @Size(min = 1, message = "El producto debe tener al menos una categoría")
    public Set<Long> categoryIds; // Múltiples categorías

}
```

### UpdateProductDto.java
```java
package ec.edu.ups.icc.fundamentos01.products.dtos;

import java.util.Set;

import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Positive;
import jakarta.validation.constraints.Size;

public class UpdateProductDto {

    @NotBlank
    @Size(min = 3, max = 150)
    public String name;

    @NotNull
    @Positive
    public Double price;

    @Size(max = 500)
    public String description;

    // ============== ACTUALIZACIÓN DE RELACIONES ==============

    // @NotNull(message = "El ID de la categoría es obligatorio")
    // public Long categoryId;

    @NotNull(message = "Debe especificar al menos una categoría")
    @Size(min = 1, message = "El producto debe tener al menos una categoría")
    public Set<Long> categoryIds; // Múltiples categorías

    // Nota: No se permite cambiar el owner de un producto una vez creado
    // Si fuera necesario, sería una operación de negocio especial
}
```

### ValidateProductNameDto.java
```java
package ec.edu.ups.icc.fundamentos01.products.dtos;

public class ValidateProductNameDto {

    public int id;
    public String name;

}
```

### ProductMapper.java
```java
package ec.edu.ups.icc.fundamentos01.products.mappers;

import ec.edu.ups.icc.fundamentos01.products.dtos.CreateProductDto;
import ec.edu.ups.icc.fundamentos01.products.dtos.UpdateProductDto;
import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;
import ec.edu.ups.icc.fundamentos01.products.models.Product;

public class ProductMapper {

    public static Product toModel(int id, String name, Double price, String description) {
        return new Product(id, name, price, description);
    }

    // DTO -> Model
    public static Product fromCreateDto(CreateProductDto dto) {
        return new Product(0, dto.name, dto.price, dto.description);
    }

    public static Product fromUpdateDto(UpdateProductDto dto) {
        return new Product(0, dto.name, dto.price, dto.description);
    }

    public static ProductResponseDto toResponse(Product product) {
        ProductResponseDto dto = new ProductResponseDto();
        dto.id = product.getId();
        dto.name = product.getName();
        dto.price = product.getPrice();
        dto.description = product.getDescription();

        // dto.user = new ProductResponseDto.UserSummaryDto();
        // dto.user.id = product.getOwner().getId();
        // dto.user.username = product.getOwner().getUsername();

        return dto;
    }
}
```

### Product.java
```java
package ec.edu.ups.icc.fundamentos01.products.models;

import java.util.Set;

import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;
import ec.edu.ups.icc.fundamentos01.products.dtos.CreateProductDto;
import ec.edu.ups.icc.fundamentos01.products.dtos.PartialUpdateProductDto;
import ec.edu.ups.icc.fundamentos01.products.dtos.UpdateProductDto;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;

public class Product {

    private Long id;
    private String name;
    private Double price;
    private String description;
    private String createdAt;

    // Constructor privado para forzar uso de factory methods
    public Product(long id, String name, Double price, String description) {
        this.id = id;
        this.name = name;
        this.price = price;
        this.description = description;
        this.createdAt = java.time.LocalDateTime.now().toString();
    }

    public Product(String name, Double price, String description) {
        this.validateBusinessRules(name, price, description);
        this.name = name;
        this.price = price;
        this.description = description;
        this.createdAt = java.time.LocalDateTime.now().toString();
    }

    private void validateBusinessRules(String name, Double price, String description) {
        if (name == null || name.trim().isEmpty()) {
            throw new IllegalArgumentException("El nombre del producto es obligatorio");
        }
        if (price == null || price <= 0) {
            throw new IllegalArgumentException("El precio debe ser mayor a 0");
        }
        if (description != null && description.length() > 500) {
            throw new IllegalArgumentException("La descripción no puede superar 500 caracteres");
        }
    }

    // ==================== FACTORY METHODS ====================

    /**
     * Convierte este Product a una entidad persistente
     * 
     * @return ProductEntity lista para guardar en BD
     */
    public ProductEntity toEntity(UserEntity owner, Set<CategoryEntity> categories) {
        ProductEntity entity = new ProductEntity();
        if (this.id != null && this.id > 0) {
            entity.setId(this.id);
        }

        entity.setName(this.name);
        entity.setPrice(this.price);
        entity.setDescription(this.description);

        // Asignar relaciones
        entity.setOwner(owner);

        entity.setCategories(categories);

        return entity;
    }

    public Product update(UpdateProductDto dto) {
        this.name = dto.name;
        this.price = dto.price;
        this.description = dto.description;
        return this;
    }

    public Product update(PartialUpdateProductDto dto) {
        this.name = dto.name;
        this.price = dto.price;
        this.description = dto.description;
        return this;
    }

    /**
     * Crea un Product desde un DTO de creación
     */
    public static Product fromDto(CreateProductDto dto) {
        return new Product(dto.name, dto.price, dto.description);
    }

    /**
     * Crea un Product desde una entidad persistente
     */
    public static Product fromEntity(ProductEntity entity) {
        Product product = new Product(
                entity.getName(),
                entity.getPrice(),
                entity.getDescription());
        product.id = entity.getId();

        return product;
    }

    public long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Double getPrice() {
        return price;
    }

    public void setPrice(Double price) {
        this.price = price;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public String getCreatedAt() {
        return createdAt;
    }

    public void setCreatedAt(String createdAt) {
        this.createdAt = createdAt;
    }

    public Product partialUpdate(PartialUpdateProductDto dto) {

        if (dto.name != null) {
            this.name = dto.name;
        }

        if (dto.price != null) {
            this.price = dto.price;
        }

        if (dto.description != null) {
            this.description = dto.description;
        }

        return this;
    }

}
```

### ProductEntity.java
```java
package ec.edu.ups.icc.fundamentos01.products.models;

import java.util.HashSet;
import java.util.Set;

import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;
import ec.edu.ups.icc.fundamentos01.core.entities.BaseModel;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import jakarta.persistence.*;

@Entity
@Table(name = "products")
public class ProductEntity extends BaseModel {

    @Column(nullable = false, length = 150)
    private String name;

    @Column(nullable = false)
    private Double price;

    @Column(length = 500)
    private String description;
    // ================== RELACIONES 1:N ==================

    /**
     * Relación Many-to-One con User
     * Muchos productos pertenecen a un usuario (owner/creator)
     */
    @ManyToOne(optional = false, fetch = FetchType.LAZY)
    @JoinColumn(name = "user_id", nullable = false)
    private UserEntity owner;

    /**
     * Relación Many-to-One con Category
     * Muchos productos pertenecen a una categoría
     */
    // @ManyToOne(optional = false, fetch = FetchType.LAZY)
    // @JoinColumn(name = "category_id", nullable = false)
    // private CategoryEntity category;

    /**
     * Relación Many-to-Many con Category
     * Un producto puede tener múltiples categorías
     * Una categoría puede estar en múltiples productos
     */
    @ManyToMany(fetch = FetchType.LAZY)
    @JoinTable(name = "product_categories", // Tabla intermedia
            joinColumns = @JoinColumn(name = "product_id"), // FK hacia products
            inverseJoinColumns = @JoinColumn(name = "category_id") // FK hacia categories
    )
    private Set<CategoryEntity> categories = new HashSet<>();

    // Constructores
    public ProductEntity() {
    }

    // ============== MÉTODOS DE CONVENIENCIA ==============
    /**
     * Remueve una categoría del producto y sincroniza la relación bidireccional
     */
    public void removeCategory(CategoryEntity category) {
        this.categories.remove(category);

    }

    /**
     * Limpia todas las categorías y sincroniza las relaciones
     */
    public void clearCategories() {
        // Luego limpiar la colección local
        this.categories.clear();
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Double getPrice() {
        return price;
    }

    public void setPrice(Double price) {
        this.price = price;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public UserEntity getOwner() {
        return owner;
    }

    public void setOwner(UserEntity owner) {
        this.owner = owner;
    }

    public Set<CategoryEntity> getCategories() {
        return categories;
    }

    public void setCategories(Set<CategoryEntity> categories) {
        this.categories = categories;
    }

    public void addCategory(CategoryEntity category) {
        this.categories.add(category);

    }

}
```

### ProductRepository.java
```java
package ec.edu.ups.icc.fundamentos01.products.repository;

import java.util.List;
import java.util.Optional;

import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.data.domain.Slice;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;
import org.springframework.stereotype.Repository;

import ec.edu.ups.icc.fundamentos01.products.models.ProductEntity;

@Repository
public interface ProductRepository extends JpaRepository<ProductEntity, Long> {

        Optional<ProductEntity> findByName(String name);

        List<ProductEntity> findByOwnerId(Long userId);

        // List<ProductEntity> findByCategoryId(Long categoryId);

        /**
         * Encuentra productos por nombre de usuario
         * Genera JOIN automáticamente:
         * SELECT p.* FROM products p JOIN users u ON p.user_id = u.id WHERE u.name = ?
         */
        List<ProductEntity> findByOwnerName(String ownerName);

        /**
         * Encuentra productos que tienen UNA categoría específica
         * Útil para filtros de categoría
         */
        List<ProductEntity> findByCategoriesId(Long categoryId);

        /**
         * Encuentra productos que tienen una categoría con nombre específico
         */
        List<ProductEntity> findByCategoriesName(String categoryName);

        /**
         * Consulta personalizada: productos con TODAS las categorías especificadas
         */
        @Query("SELECT p FROM ProductEntity p " +
                        "WHERE SIZE(p.categories) >= :categoryCount " +
                        "AND :categoryCount = " +
                        "(SELECT COUNT(c) FROM p.categories c WHERE c.id IN :categoryIds)")
        List<ProductEntity> findByAllCategories(@Param("categoryIds") List<Long> categoryIds,
                        @Param("categoryCount") long categoryCount);

        /**
         * Consulta personalizada: productos de un usuario con filtros opcionales
         * Permite filtrar por nombre, precio mínimo/máximo y categoría
         */
        @Query("SELECT DISTINCT p FROM ProductEntity p " +
                        "LEFT JOIN p.categories c " +
                        "WHERE p.owner.id = :userId " +
                        "AND (COALESCE(:name, '') = '' OR LOWER(p.name) LIKE LOWER(CONCAT('%', :name, '%'))) " +
                        "AND (:minPrice IS NULL OR p.price >= :minPrice) " +
                        "AND (:maxPrice IS NULL OR p.price <= :maxPrice) " +
                        "AND (:categoryId IS NULL OR c.id = :categoryId)")
        List<ProductEntity> findByOwnerIdWithFilters(
                        @Param("userId") Long userId,
                        @Param("name") String name,
                        @Param("minPrice") Double minPrice,
                        @Param("maxPrice") Double maxPrice,
                        @Param("categoryId") Long categoryId);

        /**
         * Busca productos por nombre de usuario con paginación
         */
        @Query("SELECT p FROM ProductEntity p " +
                        "JOIN p.owner o WHERE LOWER(o.name) LIKE LOWER(CONCAT('%', :ownerName, '%'))")
        Page<ProductEntity> findByOwnerNameContaining(@Param("ownerName") String ownerName, Pageable pageable);

        // ============== CONSULTA COMPLEJA CON FILTROS Y PAGINACIÓN ==============

        /**
         * Busca productos con filtros opcionales y paginación
         * Todos los parámetros son opcionales excepto el Pageable
         * NOTA: Usa LEFT JOIN p.categories para relación Many-to-Many
         */
        @Query("SELECT DISTINCT p FROM ProductEntity p " +
                        "LEFT JOIN p.categories c " +
                        "WHERE (COALESCE(:name, '') = '' OR LOWER(p.name) LIKE LOWER(CONCAT('%', :name, '%'))) " +
                        "AND (:minPrice IS NULL OR p.price >= :minPrice) " +
                        "AND (:maxPrice IS NULL OR p.price <= :maxPrice) " +
                        "AND (:categoryId IS NULL OR c.id = :categoryId)")
        Page<ProductEntity> findWithFilters(
                        @Param("name") String name,
                        @Param("minPrice") Double minPrice,
                        @Param("maxPrice") Double maxPrice,
                        @Param("categoryId") Long categoryId,
                        Pageable pageable);

        /**
         * Busca productos de un usuario con filtros opcionales y paginación
         * NOTA: Usa LEFT JOIN p.categories para relación Many-to-Many
         */
        @Query("SELECT DISTINCT p FROM ProductEntity p " +
                        "LEFT JOIN p.categories c " +
                        "WHERE p.owner.id = :userId " +
                        "AND (COALESCE(:name, '') = '' OR LOWER(p.name) LIKE LOWER(CONCAT('%', :name, '%'))) " +
                        "AND (:minPrice IS NULL OR p.price >= :minPrice) " +
                        "AND (:maxPrice IS NULL OR p.price <= :maxPrice) " +
                        "AND (:categoryId IS NULL OR c.id = :categoryId)")
        Page<ProductEntity> findByUserIdWithFilters(
                        @Param("userId") Long userId,
                        @Param("name") String name,
                        @Param("minPrice") Double minPrice,
                        @Param("maxPrice") Double maxPrice,
                        @Param("categoryId") Long categoryId,
                        Pageable pageable);

        Slice<ProductEntity> findBy(Pageable pageable);
```

### ProductService.java
```java
package ec.edu.ups.icc.fundamentos01.products.services;

import java.util.List;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Slice;
import ec.edu.ups.icc.fundamentos01.products.dtos.CreateProductDto;
import ec.edu.ups.icc.fundamentos01.products.dtos.UpdateProductDto;
import ec.edu.ups.icc.fundamentos01.security.service.UserDetailsImpl;
import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;

public interface ProductService {

        ProductResponseDto create(CreateProductDto dto);

        List<ProductResponseDto> findAll();

        ProductResponseDto findById(Long id);

        List<ProductResponseDto> findByUserId(Long id);

        List<ProductResponseDto> findByCategoryId(Long id);

        ProductResponseDto update(Long id, UpdateProductDto dto, UserDetailsImpl currentUser);

        void delete(Long id, UserDetailsImpl currentUser );

        Page<ProductResponseDto> findAllPaginado(int page, int size, String[] sort);

        Slice<ProductResponseDto> findAllSlice(int page, int size, String[] sort);

        Page<ProductResponseDto> findWithFilters(String name, Double minPrice, Double maxPrice, Long categoryId,
                        int page,
                        int size, String[] sort);

        Page<ProductResponseDto> findByUserIdWithFilters(Long userId, String name, Double minPrice, Double maxPrice,
                        Long categoryId, int page, int size, String[] sort);

}
```

### ProductServiceImpl.java
```java
package ec.edu.ups.icc.fundamentos01.products.services;

import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;
import java.util.Set;

import org.springframework.data.domain.Page;
import org.springframework.data.domain.PageRequest;
import org.springframework.data.domain.Pageable;
import org.springframework.data.domain.Slice;
import org.springframework.data.domain.Sort;
import org.springframework.security.access.AccessDeniedException;
import org.springframework.security.core.GrantedAuthority;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;
import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;
import ec.edu.ups.icc.fundamentos01.categories.reporitory.CategoryRepository;
import ec.edu.ups.icc.fundamentos01.exceptions.domain.BadRequestException;
import ec.edu.ups.icc.fundamentos01.exceptions.domain.NotFoundException;
import ec.edu.ups.icc.fundamentos01.products.dtos.CreateProductDto;

import ec.edu.ups.icc.fundamentos01.products.dtos.UpdateProductDto;
import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;

import ec.edu.ups.icc.fundamentos01.products.models.Product;
import ec.edu.ups.icc.fundamentos01.products.models.ProductEntity;
import ec.edu.ups.icc.fundamentos01.products.repository.ProductRepository;
import ec.edu.ups.icc.fundamentos01.security.service.UserDetailsImpl;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import ec.edu.ups.icc.fundamentos01.users.repository.UserRepository;

@Service
public class ProductServiceImpl implements ProductService {

    private final ProductRepository productRepo;

    private final UserRepository userRepo;

    private final CategoryRepository categoryRepo;

    public ProductServiceImpl(ProductRepository productRepo,
            UserRepository userRepo,
            CategoryRepository categoryRepository) {
        this.productRepo = productRepo;
        this.categoryRepo = categoryRepository;
        this.userRepo = userRepo;
    }

    @Override
    public ProductResponseDto create(CreateProductDto dto) {

        // 1. VALIDAR EXISTENCIA DE RELACIONES
        UserEntity owner = userRepo.findById(dto.userId)
                .orElseThrow(() -> new NotFoundException("Usuario no encontrado con ID: " + dto.userId));

        // 2. VALIDAR Y OBTENER CATEGORÍAS
        Set<CategoryEntity> categories = validateAndGetCategories(dto.categoryIds);

        // Regla: nombre único
        if (productRepo.findByName(dto.name).isPresent()) {
            throw new IllegalStateException("El nombre del producto ya está registrado");
        }

        // 2. CREAR MODELO DE DOMINIO
        Product product = Product.fromDto(dto);

        // 3. CONVERTIR A ENTIDAD CON RELACIONES
        ProductEntity entity = product.toEntity(owner, categories);

        // 4. PERSISTIR
        ProductEntity saved = productRepo.save(entity);

        // 5. CONVERTIR A DTO DE RESPUESTA
        return toResponseDto(saved);
    }

    @Override
    public List<ProductResponseDto> findAll() {
        return productRepo.findAll()
                .stream()
                .map(this::toResponseDto)
                .toList();
    }

    // ============== MÉTODOS HELPER ==============

    @Override
    public ProductResponseDto findById(Long id) {
        return productRepo.findById(id)
                .map(this::toResponseDto)
                .orElseThrow(() -> new NotFoundException("Producto no encontrado con ID: " + id));
    }

    @Override
    public List<ProductResponseDto> findByUserId(Long userId) {

        // Validar que el usuario existe
        if (!userRepo.existsById(userId)) {
            throw new NotFoundException("Usuario no encontrado con ID: " + userId);
        }

        return productRepo.findByOwnerId(userId)
                .stream()
                .map(this::toResponseDto)
                .toList();
    }

    @Override
    public List<ProductResponseDto> findByCategoryId(Long categoryId) {

        // Validar que la categoría existe
        if (!categoryRepo.existsById(categoryId)) {
            throw new NotFoundException("Categoría no encontrada con ID: " + categoryId);
        }

        return productRepo.findByCategoriesId(categoryId)
                .stream()
                .map(this::toResponseDto)
                .toList();
    }

    @Override
    @Transactional
    public ProductResponseDto update(Long id, UpdateProductDto dto, UserDetailsImpl currentUser) {

        // 1. BUSCAR PRODUCTO EXISTENTE
        ProductEntity existing = productRepo.findById(id)
                .orElseThrow(() -> new NotFoundException("Producto no encontrado con ID: " + id));

        // 2. VALIDAR Y OBTENER CATEGORÍAS
        Set<CategoryEntity> categories = validateAndGetCategories(dto.categoryIds);

        // 3. ACTUALIZAR USANDO DOMINIO
        Product product = Product.fromEntity(existing);
        product.update(dto);

        // 4. CONVERTIR A ENTIDAD MANTENIENDO OWNER ORIGINAL
        ProductEntity updated = product.toEntity(existing.getOwner(), categories);
        updated.setId(id); // Asegurar que mantiene el ID

        // 5. PERSISTIR Y RESPONDER
        ProductEntity saved = productRepo.save(updated);
        return toResponseDto(saved);
    }

    @Override
    @Transactional
    public void delete(Long id, UserDetailsImpl currentUser) {

        ProductEntity product = productRepo.findById(id)
                .orElseThrow(() -> new NotFoundException("Producto no encontrado con ID: " + id));

        // Eliminación física (también se puede implementar lógica)
        productRepo.delete(product);
    }

    private ProductResponseDto toResponseDto(ProductEntity entity) {
        ProductResponseDto dto = new ProductResponseDto();
        dto.id = entity.getId();
        dto.name = entity.getName();
        dto.price = entity.getPrice();
        dto.description = entity.getDescription();

        ProductResponseDto.UserSummaryDto ownerDto = new ProductResponseDto.UserSummaryDto();
        ownerDto.id = entity.getOwner().getId();
        ownerDto.name = entity.getOwner().getName();

        List<CategoryResponseDto> categoryDtos = new ArrayList<>();
        for (CategoryEntity categoryEntity : entity.getCategories()) {
            CategoryResponseDto categoryDto = new CategoryResponseDto();
            categoryDto.id = categoryEntity.getId();
            categoryDto.name = categoryEntity.getName();
            categoryDtos.add(categoryDto);
        }
        dto.user = ownerDto;
        dto.categories = categoryDtos;
        return dto;

    }

    private Set<CategoryEntity> validateAndGetCategories(Set<Long> categoryIds) {
        Set<CategoryEntity> categories = new HashSet<>();

        for (Long categoryId : categoryIds) {
            CategoryEntity category = categoryRepo.findById(categoryId)
                    .orElseThrow(() -> new NotFoundException("Categoría no encontrada: " + categoryId));
            categories.add(category);
        }

        return categories;
    }

    // private Pageable createPageable(int page, int size, String[] sort) {
    //     // Validar parámetros
    //     if (page < 0) {
    //         throw new BadRequestException("La página debe ser mayor o igual a 0");
    //     }
    //     if (size < 1 || size > 100) {
    //         throw new BadRequestException("El tamaño debe estar entre 1 y 100");
    //     }

    //     // Crear Sort
    //     Sort sortObj = createSort(sort);

    //     return PageRequest.of(page, size, sortObj);
    // }

    private Sort createSort(String[] sort) {
        if (sort == null || sort.length == 0) {
            return Sort.by("id");
        }

        List<Sort.Order> orders = new ArrayList<>();
        for (String sortParam : sort) {
            String[] parts = sortParam.split(",");
            String property = parts[0];
            String direction = parts.length > 1 ? parts[1] : "asc";

            // Validar propiedades permitidas para evitar inyección SQL
            if (!isValidSortProperty(property)) {
                throw new BadRequestException("Propiedad de ordenamiento no válida: " + property);
            }

            Sort.Order order = "desc".equalsIgnoreCase(direction)
                    ? Sort.Order.desc(property)
                    : Sort.Order.asc(property);

            orders.add(order);
        }

        return Sort.by(orders);
    }

    private boolean isValidSortProperty(String property) {
        // Lista blanca de propiedades permitidas para ordenamiento
        Set<String> allowedProperties = Set.of(
                "id", "name", "price", "createdAt", "updatedAt",
                "owner.name", "owner.email", "category.name");
        return allowedProperties.contains(property);
    }

    private void validateFilterParameters(Double minPrice, Double maxPrice) {
        if (minPrice != null && minPrice < 0) {
            throw new BadRequestException("El precio mínimo no puede ser negativo");
        }

        if (maxPrice != null && maxPrice < 0) {
            throw new BadRequestException("El precio máximo no puede ser negativo");
        }

        if (minPrice != null && maxPrice != null && maxPrice < minPrice) {
            throw new BadRequestException("El precio máximo debe ser mayor o igual al precio mínimo");
        }
    }

    @Override
    public Page<ProductResponseDto> findAllPaginado(int page, int size, String[] sort) {
        Pageable pageable = createPageable(page, size, sort);
        Page<ProductEntity> productPage = productRepo.findAll(pageable);

        return productPage.map(this::toResponseDto);
    }

    @Override
    public Slice<ProductResponseDto> findAllSlice(int page, int size, String[] sort) {
        Pageable pageable = createPageable(page, size, sort);
        Slice<ProductEntity> productSlice = productRepo.findBy(pageable);
        return productSlice.map(this::toResponseDto);
    }

    @Override
    public Page<ProductResponseDto> findWithFilters(String name, Double minPrice, Double maxPrice, Long categoryId,
            int page, int size, String[] sort) {

        // Validaciones de filtros (del tema 09)
        validateFilterParameters(minPrice, maxPrice);

        // Crear Pageable
        Pageable pageable = createPageable(page, size, sort);

        // Consulta con filtros y paginación
        Page<ProductEntity> productPage = productRepo.findWithFilters(
                name, minPrice, maxPrice, categoryId, pageable);

        return productPage.map(this::toResponseDto);
    }

    @Override
    public Page<ProductResponseDto> findByUserIdWithFilters(Long userId, String name, Double minPrice, Double maxPrice,
            Long categoryId, int page, int size, String[] sort) {
        // 1. Validar que el usuario existe
        if (!userRepo.existsById(userId)) {
            throw new NotFoundException("Usuario no encontrado con ID: " + userId);
        }

        // 2. Validar filtros
        validateFilterParameters(minPrice, maxPrice);

        // 3. Crear Pageable
        Pageable pageable = createPageable(page, size, sort);

        // 4. Consulta con filtros y paginación
        Page<ProductEntity> productPage = productRepo.findByUserIdWithFilters(
                userId, name, minPrice, maxPrice, categoryId, pageable);

        return productPage.map(this::toResponseDto);
    }

    // ============== MÉTODOS DE VALIDACIÓN Y UTILIDADES ==============

    /**
     * Valida si el usuario puede modificar/eliminar el producto
     * 
     * Lógica:
     * 1. Si tiene ROLE_ADMIN → Puede modificar cualquier producto
     * 2. Si tiene ROLE_MODERATOR → Puede modificar cualquier producto
     * 3. Si es ROLE_USER → Solo puede modificar sus propios productos
     * 
     * @param product Producto a validar
     * @param currentUser Usuario autenticado (del JWT)
     * @throws AccessDeniedException si no tiene permisos
     */
    private void validateOwnership(ProductEntity product, UserDetailsImpl currentUser) {
        // ADMIN y MODERATOR pueden modificar cualquier producto
        if (hasAnyRole(currentUser, "ROLE_ADMIN", "ROLE_MODERATOR")) {
            return;  // ← Pasa la validación automáticamente
        }

        // USER solo puede modificar sus propios productos
        if (!product.getOwner().getId().equals(currentUser.getId())) {
            // ← Lanza excepción que será capturada por GlobalExceptionHandler
            throw new AccessDeniedException("No puedes modificar productos ajenos");
        }

        // Si llega aquí, es el dueño → Pasa la validación
    }

    /**
     * Verifica si el usuario tiene alguno de los roles especificados
     * 
     * @param user Usuario a verificar
     * @param roles Roles a buscar
     * @return true si tiene al menos uno de los roles
     */
    private boolean hasAnyRole(UserDetailsImpl user, String... roles) {
        for (String role : roles) {
            for (GrantedAuthority authority : user.getAuthorities()) {
                if (authority.getAuthority().equals(role)) {
                    return true;
                }
            }
        }
        return false;
    }

 

    /**
     * Crea Pageable con ordenamiento dinámico
     */
    private Pageable createPageable(int page, int size, String[] sort) {
        String sortField = sort[0];
        Sort.Direction sortDirection = sort.length > 1 && sort[1].equalsIgnoreCase("desc")
                ? Sort.Direction.DESC
                : Sort.Direction.ASC;

        return PageRequest.of(page, size, Sort.by(sortDirection, sortField));
    }
```

### JacksonConfig.java
```java
package ec.edu.ups.icc.fundamentos01.security.config;

// imports packages y clases....

import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.SerializationFeature;
import com.fasterxml.jackson.datatype.jsr310.JavaTimeModule;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Primary;

@Configuration
public class JacksonConfig {

    /**
     * Configura ObjectMapper global para toda la aplicación
     * 
     * @Primary: Marca este bean como el ObjectMapper principal
     * Se usa automáticamente en:
     * - @RestController para serializar respuestas
     * - JwtAuthenticationEntryPoint para serializar errores
     * - Cualquier componente que inyecte ObjectMapper
     */
    @Bean
    @Primary
    public ObjectMapper objectMapper() {
        ObjectMapper mapper = new ObjectMapper();

        // ============== CONFIGURACIÓN CRÍTICA ==============
        
        // Registrar módulo para manejo de fechas Java 8+
        // Permite serializar: LocalDateTime, LocalDate, LocalTime, Instant, etc.
        mapper.registerModule(new JavaTimeModule());

        // Serializar fechas como ISO-8601 ("2024-01-26T10:30:00")
        // En lugar de timestamp numérico (1706268600000)
        mapper.disable(SerializationFeature.WRITE_DATES_AS_TIMESTAMPS);

        // ============== CONFIGURACIONES OPCIONALES ==============
        
        // No fallar si un bean está vacío (sin propiedades)
        mapper.configure(SerializationFeature.FAIL_ON_EMPTY_BEANS, false);
        
        // Indentar JSON para mejor legibilidad (opcional, desactivar en producción)
        // mapper.enable(SerializationFeature.INDENT_OUTPUT);

        return mapper;
    }
}```

### JwtProperties.java
```java
package ec.edu.ups.icc.fundamentos01.security.config;

// imports packages y clases....

import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.context.annotation.Configuration;

@Configuration
@ConfigurationProperties(prefix = "jwt")
public class JwtProperties {

    private String secret;
    private Long expiration;
    private Long refreshExpiration;
    private String issuer;
    private String header;
    private String prefix;

    // Getters y Setters

    public String getSecret() {
        return secret;
    }

    public void setSecret(String secret) {
        this.secret = secret;
    }

    public Long getExpiration() {
        return expiration;
    }

    public void setExpiration(Long expiration) {
        this.expiration = expiration;
    }

    public Long getRefreshExpiration() {
        return refreshExpiration;
    }

    public void setRefreshExpiration(Long refreshExpiration) {
        this.refreshExpiration = refreshExpiration;
    }

    public String getIssuer() {
        return issuer;
    }

    public void setIssuer(String issuer) {
        this.issuer = issuer;
    }

    public String getHeader() {
        return header;
    }

    public void setHeader(String header) {
        this.header = header;
    }

    public String getPrefix() {
        return prefix;
    }

    public void setPrefix(String prefix) {
        this.prefix = prefix;
    }

}
```

### SecurityConfig.java
```java
package ec.edu.ups.icc.fundamentos01.security.config;

// imports packages y clases....

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.authentication.AuthenticationManager;
import org.springframework.security.authentication.dao.DaoAuthenticationProvider;
import org.springframework.security.config.annotation.authentication.configuration.AuthenticationConfiguration;
import org.springframework.security.config.annotation.method.configuration.EnableMethodSecurity;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
import org.springframework.security.config.annotation.web.configurers.AbstractHttpConfigurer;
import org.springframework.security.config.http.SessionCreationPolicy;
import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.security.web.SecurityFilterChain;
import org.springframework.security.web.authentication.UsernamePasswordAuthenticationFilter;

import ec.edu.ups.icc.fundamentos01.security.filters.JwtAuthenticationEntryPoint;
import ec.edu.ups.icc.fundamentos01.security.filters.JwtAuthenticationFilter;
import ec.edu.ups.icc.fundamentos01.security.service.UserDetailsServiceImpl;

@Configuration
@EnableWebSecurity
@EnableMethodSecurity(prePostEnabled = true)
public class SecurityConfig {

    private final UserDetailsServiceImpl userDetailsService;
    private final JwtAuthenticationEntryPoint unauthorizedHandler;
    private final JwtAuthenticationFilter jwtAuthenticationFilter;

    public SecurityConfig(UserDetailsServiceImpl userDetailsService,
            JwtAuthenticationEntryPoint unauthorizedHandler,
            JwtAuthenticationFilter jwtAuthenticationFilter) {
        this.userDetailsService = userDetailsService;
        this.unauthorizedHandler = unauthorizedHandler;
        this.jwtAuthenticationFilter = jwtAuthenticationFilter;
    }

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }

    /**
     * DaoAuthenticationProvider: Proveedor de autenticación que conecta:
     * - UserDetailsService: Carga información del usuario desde BD
     * - PasswordEncoder: Valida la contraseña hasheada
     * 
     * Spring Security usa este provider para autenticar credenciales.
     * El constructor acepta directamente el UserDetailsService en Spring Boot
     * 3.x/4.x
     */
    @Bean
    public DaoAuthenticationProvider authenticationProvider() {
        DaoAuthenticationProvider authProvider = new DaoAuthenticationProvider(userDetailsService);
        authProvider.setPasswordEncoder(passwordEncoder());
        return authProvider;
    }

    @Bean
    public AuthenticationManager authenticationManager(AuthenticationConfiguration authConfig) throws Exception {
        return authConfig.getAuthenticationManager();
    }

    // @Bean
    // public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
    // http
    // // Deshabilitar CSRF (no necesario para APIs REST con JWT)
    // .csrf(AbstractHttpConfigurer::disable)

    // // Configurar manejo de excepciones de autenticación
    // .exceptionHandling(exception -> exception
    // .authenticationEntryPoint(unauthorizedHandler)
    // )

    // // Configurar sesiones como stateless (no usar sesiones HTTP)
    // .sessionManagement(session -> session
    // .sessionCreationPolicy(SessionCreationPolicy.STATELESS)
    // )

    // // Configurar autorización de requests
    // .authorizeHttpRequests(auth -> auth
    // // Endpoints públicos (sin autenticación)
    // .requestMatchers("/auth/**").permitAll()
    // .requestMatchers("/status/**").permitAll()
    // .requestMatchers("/actuator/**").permitAll()

    // // Todos los demás endpoints requieren autenticación
    // .anyRequest().authenticated()
    // );

    // // Agregar proveedor de autenticación
    // http.authenticationProvider(authenticationProvider());

    // // Agregar filtro JWT antes del filtro de autenticación estándar
    // http.addFilterBefore(jwtAuthenticationFilter,
    // UsernamePasswordAuthenticationFilter.class);

    // return http.build();
    // }
    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
                .csrf(AbstractHttpConfigurer::disable)
                .exceptionHandling(exception -> exception
                        .authenticationEntryPoint(unauthorizedHandler))
                .sessionManagement(session -> session
                        .sessionCreationPolicy(SessionCreationPolicy.STATELESS))
                .authorizeHttpRequests(auth -> auth
                        // Endpoints públicos
                        .requestMatchers("/auth/**").permitAll()
                        .requestMatchers("/status/**").permitAll()

                        // Endpoints por rol
                        .requestMatchers("/api/admin/**").hasRole("ADMIN")
                        .requestMatchers("/api/moderator/**").hasAnyRole("ADMIN", "MODERATOR")

                        // Resto requiere autenticación
                        .anyRequest().authenticated())
                .addFilterBefore(jwtAuthenticationFilter, UsernamePasswordAuthenticationFilter.class);

        return http.build();
    }
}```

### AuthController.java
```java
package ec.edu.ups.icc.fundamentos01.security.controllers;
// imports packages y clases....

import jakarta.validation.Valid;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import ec.edu.ups.icc.fundamentos01.security.dtos.AuthResponseDto;
import ec.edu.ups.icc.fundamentos01.security.dtos.LoginRequestDto;
import ec.edu.ups.icc.fundamentos01.security.dtos.RegisterRequestDto;
import ec.edu.ups.icc.fundamentos01.security.service.AuthService;

@RestController
@RequestMapping("/auth") // Prefijo para todos los endpoints de autenticación
public class AuthController {

    private final AuthService authService; // Servicio de lógica de autenticación

    public AuthController(AuthService authService) {
        this.authService = authService;
    }

    /**
     * Login - Endpoint público (configurado en SecurityConfig)
     * POST /auth/login
     */
    @PostMapping("/login")
    public ResponseEntity<AuthResponseDto> login(@Valid @RequestBody LoginRequestDto loginRequest) {
        // @Valid valida anotaciones en LoginRequestDto (email, password requeridos)
        AuthResponseDto response = authService.login(loginRequest);
        return ResponseEntity.ok(response); // 200 OK con JWT
    }

    /**
     * Registro - Endpoint público (configurado en SecurityConfig)
     * POST /auth/register
     */
    @PostMapping("/register")
    public ResponseEntity<AuthResponseDto> register(@Valid @RequestBody RegisterRequestDto registerRequest) {
        // @Valid valida anotaciones en RegisterRequestDto
        AuthResponseDto response = authService.register(registerRequest);
        return ResponseEntity.status(HttpStatus.CREATED).body(response); // 201 Created con JWT
    }
}```

### AutResponseDto.java
package ec.edu.ups.icc.fundamentos01.security.dtos;

// imports packages y clases....


import java.util.Set;

public class AuthResponseDto {

    private String token;
    private String type = "Bearer";
    private Long userId;
    private String name;
    private String email;
    private Set<String> roles;

    // Constructores
    public AuthResponseDto() {
    }

    public AuthResponseDto(String token, Long userId, String name, String email, Set<String> roles) {
        this.token = token;
        this.userId = userId;
        this.name = name;
        this.email = email;
        this.roles = roles;
    }

    public String getToken() {
        return token;
    }

    public void setToken(String token) {
        this.token = token;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
        this.type = type;
    }

    public Long getUserId() {
        return userId;
    }

    public void setUserId(Long userId) {
        this.userId = userId;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public Set<String> getRoles() {
        return roles;
    }

    public void setRoles(Set<String> roles) {
        this.roles = roles;
    }

    // Getters y Setters
  
    
}

### LoginResquestDto.java

package ec.edu.ups.icc.fundamentos01.security.dtos;

import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.Size;

public class LoginRequestDto {

    @NotBlank(message = "El email es obligatorio")
    @Email(message = "El email debe ser válido")
    private String email;

    @NotBlank(message = "La contraseña es obligatoria")
    @Size(min = 6, message = "La contraseña debe tener al menos 6 caracteres")
    private String password;

    // Constructores
    public LoginRequestDto() {
    }

    public LoginRequestDto(String email, String password) {
        this.email = email;
        this.password = password;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    // Getters y Setters

    
}

### ResgisterRequestDto.java
package ec.edu.ups.icc.fundamentos01.security.dtos;

// imports packages y clases....


import jakarta.validation.constraints.*;

public class RegisterRequestDto {

    @NotBlank(message = "El nombre es obligatorio")
    @Size(min = 3, max = 150, message = "El nombre debe tener entre 3 y 150 caracteres")
    private String name;

    @NotBlank(message = "El email es obligatorio")
    @Email(message = "El email debe ser válido")
    @Size(max = 150, message = "El email no puede exceder 150 caracteres")
    private String email;

    @NotBlank(message = "La contraseña es obligatoria")
    @Size(min = 6, max = 100, message = "La contraseña debe tener entre 6 y 100 caracteres")
    @Pattern(
        regexp = "^(?=.*[0-9])(?=.*[a-z])(?=.*[A-Z]).*$",
        message = "La contraseña debe contener al menos una mayúscula, una minúscula y un número"
    )
    private String password;

    // Constructores
    public RegisterRequestDto() {
    }

    public RegisterRequestDto(String name, String email, String password) {
        this.name = name;
        this.email = email;
        this.password = password;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    // Getters y Setters
  
    
}

### JwtAuthenticationEntryPoint.java
```java
package ec.edu.ups.icc.fundamentos01.security.filters;

// imports packages y clases....

import com.fasterxml.jackson.databind.ObjectMapper;

import ec.edu.ups.icc.fundamentos01.exceptions.response.ErrorResponse;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.http.HttpStatus;
import org.springframework.http.MediaType;
import org.springframework.security.core.AuthenticationException;
import org.springframework.security.web.AuthenticationEntryPoint;
import org.springframework.stereotype.Component;

import java.io.IOException;

/**
 * JwtAuthenticationEntryPoint: Maneja errores de autenticación
 * 
 * PROPÓSITO:
 * - Capturar TODOS los errores de autenticación
 * - Retornar respuesta JSON consistente con formato 401 Unauthorized
 * - Reemplazar el comportamiento por defecto de Spring Security
 * 
 * ¿CUÁNDO SE EJECUTA?
 * - Cuando NO hay token JWT en request a endpoint protegido
 * - Cuando el token JWT es inválido (firma incorrecta, expirado, malformado)
 * - Cuando JwtAuthenticationFilter NO establece autenticación en SecurityContext
 * - Cuando Spring Security detecta falta de autenticación
 * 
 * ¿POR QUÉ NO USAR @RestControllerAdvice?
 * - @RestControllerAdvice captura excepciones DENTRO de controladores
 * - AuthenticationException se lanza ANTES de llegar al controlador
 * - Ocurre en la cadena de FILTROS de seguridad
 * - Por eso necesitamos AuthenticationEntryPoint
 * 
 * DIFERENCIA CON GlobalExceptionHandler:
 * ┌──────────────────────────────────────────────────────────┐
 * │ Request → Filtros → ¿Autenticado? → Controlador → Response│
 * │            ↑                          ↑                   │
 * │     AuthenticationEntryPoint    @RestControllerAdvice    │
 * │     (errores ANTES controlador) (errores EN controlador) │
 * └──────────────────────────────────────────────────────────┘
 * 
 * INTERFAZ AuthenticationEntryPoint:
 * - Parte de Spring Security
 * - Se configura en SecurityConfig con:
 *   .exceptionHandling(ex -> ex.authenticationEntryPoint(jwtAuthenticationEntryPoint))
 * - Método principal: commence() → Se ejecuta cuando falla autenticación
 */
@Component  // Spring lo registra como bean para inyección
public class JwtAuthenticationEntryPoint implements AuthenticationEntryPoint {

    /**
     * Logger para registrar errores de autenticación
     * 
     * Útil para:
     * - Debugging de problemas de autenticación
     * - Auditoría de intentos de acceso no autorizados
     * - Monitoreo de ataques (múltiples 401 desde misma IP)
     */
    private static final Logger logger = LoggerFactory.getLogger(JwtAuthenticationEntryPoint.class);

    /**
     * ObjectMapper: Convierte objetos Java a JSON
     * 
     * Jackson ObjectMapper:
     * - Serializa ErrorResponse a JSON
     * - Configurado automáticamente por Spring Boot
     * - Incluye JavaTimeModule para fechas
     * 
     * Inyección:
     * - Spring proporciona su ObjectMapper configurado
     * - Es el MISMO ObjectMapper que usan los @RestController
     * - Garantiza consistencia en formato de respuestas
     */
    private final ObjectMapper objectMapper;

    /**
     * Constructor: Inyección de dependencias
     * 
     * Spring inyecta su ObjectMapper configurado
     */
    public JwtAuthenticationEntryPoint(ObjectMapper objectMapper) {
        this.objectMapper = objectMapper;
    }

    /**
     * commence: MÉTODO PRINCIPAL que maneja errores de autenticación
     * 
     * Se ejecuta AUTOMÁTICAMENTE cuando:
     * 1. JwtAuthenticationFilter NO encuentra token válido
     * 2. SecurityContext está VACÍO al llegar a endpoint protegido
     * 3. Spring Security detecta falta de autenticación
     * 
     * FLUJO:
     * 1. Spring Security detecta falta de autenticación
     * 2. Llama a commence() con detalles del error
     * 3. Este método construye respuesta JSON 401
     * 4. Escribe respuesta directamente en HttpServletResponse
     * 5. La request se termina (NO llega al controlador)
     * 
     * @param request: Petición HTTP que causó el error
     * @param response: Respuesta HTTP donde escribimos el error
     * @param authException: Excepción de autenticación con detalles del error
     * 
     * IMPORTANTE:
     * - Este método escribe DIRECTAMENTE en response
     * - NO retorna nada (void)
     * - Después de ejecutar, la request se termina
     * - El controlador NUNCA se ejecuta
     */
    @Override
    public void commence(HttpServletRequest request,
                         HttpServletResponse response,
                         AuthenticationException authException) throws IOException, ServletException {

        /**
         * 1. Loguear el error
         * 
         * logger.error():
         * - Registra error en logs de aplicación
         * - Incluye mensaje de la excepción
         * - Útil para debugging y auditoría
         * 
         * authException.getMessage():
         * - Descripción del error de autenticación
         * - Ejemplos:
         *   * "Full authentication is required to access this resource"
         *   * "JWT token is expired"
         *   * "Bad credentials"
         * 
         * Ejemplo de log:
         * ERROR JwtAuthenticationEntryPoint - Error de autenticación: 
         *   Full authentication is required to access this resource
         */
        logger.error("Error de autenticación: {}", authException.getMessage());

        /**
         * 2. Crear respuesta de error estructurada
         * 
         * ErrorResponse:
         * - Clase personalizada de nuestro GlobalExceptionHandler
         * - Formato CONSISTENTE con otros errores de la API
         * - Incluye: status, message, timestamp, path
         * 
         * ¿Por qué usar ErrorResponse?
         * - Consistencia: Mismo formato para todos los errores
         * - Reutilización: Ya existe en GlobalExceptionHandler
         * - Claridad: Cliente recibe estructura conocida
         * 
         * Estructura de ErrorResponse:
         * {
         *   "timestamp": "2024-01-15T10:30:00",
         *   "status": 401,
         *   "error": "Unauthorized",
         *   "message": "Token de autenticación inválido...",
         *   "path": "/api/products"
         * }
         * 
         * Parámetros:
         * 1. HttpStatus.UNAUTHORIZED = 401
         * 2. Mensaje descriptivo en español
         * 3. request.getRequestURI() = path del endpoint que causó error
         * 
         * Mensaje detallado:
         * - Explica QUÉ salió mal: "Token inválido o no proporcionado"
         * - Explica CÓMO solucionarlo: "Debe incluir token en header"
         * - Muestra formato esperado: "Authorization: Bearer <token>"
         */
        ErrorResponse errorResponse = new ErrorResponse(
            HttpStatus.UNAUTHORIZED,  // Status 401
            "Token de autenticación inválido o no proporcionado. " +
                "Debe incluir un token válido en el header Authorization: Bearer <token>",
            request.getRequestURI()   // Path del endpoint (ej: /api/products)
        );

        /**
         * 3. Configurar Content-Type de la respuesta
         * 
         * MediaType.APPLICATION_JSON_VALUE = "application/json"
         * 
         * ¿Por qué es importante?
         * - Cliente sabrá que la respuesta es JSON
         * - Navegadores/clientes parsearán como JSON automáticamente
         * - Evita errores de parsing en frontend
         * 
         * Si olvidamos esto:
         * - Content-Type sería "text/html" por defecto
         * - Cliente intentaría parsear JSON como HTML
         * - Errores en frontend: "Unexpected token < in JSON"
         */
        response.setContentType(MediaType.APPLICATION_JSON_VALUE);

        /**
         * 4. Establecer código de estado HTTP
         * 
         * HttpServletResponse.SC_UNAUTHORIZED = 401
         * 
         * Códigos de autenticación:
         * - 401 Unauthorized: Falta autenticación o token inválido
         * - 403 Forbidden: Autenticado pero sin permisos (lo maneja Spring Security)
         * 
         * ¿Qué ve el cliente?
         * HTTP/1.1 401 Unauthorized
         * Content-Type: application/json
         * { "status": 401, "message": "..." }
         */
        response.setStatus(HttpServletResponse.SC_UNAUTHORIZED);

        /**
         * 5. Escribir JSON en la respuesta
         * 
         * objectMapper.writeValueAsString(errorResponse):
         * - Convierte ErrorResponse a String JSON
         * - Usa configuración de Jackson (fechas, null handling, etc.)
         * 
         * response.getWriter().write(...):
         * - Escribe el JSON en el cuerpo de la respuesta
         * - PrintWriter escribe directamente en el stream de salida
         * - La respuesta se envía al cliente
         * 
         * Resultado final enviado al cliente:
         * HTTP/1.1 401 Unauthorized
         * Content-Type: application/json
         * 
         * {
         *   "timestamp": "2024-01-15T10:30:00",
         *   "status": 401,
         *   "error": "Unauthorized",
         *   "message": "Token de autenticación inválido o no proporcionado. Debe incluir un token válido en el header Authorization: Bearer <token>",
         *   "path": "/api/products"
         * }
         * 
         * IMPORTANTE:
         * - Después de esto, la request se termina
         * - El controlador NUNCA se ejecuta
         * - No hay más filtros que procesen esta request
         */
        response.getWriter().write(objectMapper.writeValueAsString(errorResponse));
    }
}```
### JwtAuthenticationFilter.java
```java
package ec.edu.ups.icc.fundamentos01.security.filters;

// imports packages y clases....
import jakarta.servlet.FilterChain;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.security.core.userdetails.UserDetails;
import org.springframework.security.web.authentication.WebAuthenticationDetailsSource;
import org.springframework.stereotype.Component;
import org.springframework.util.StringUtils;
import org.springframework.web.filter.OncePerRequestFilter;

import ec.edu.ups.icc.fundamentos01.security.config.JwtProperties;
import ec.edu.ups.icc.fundamentos01.security.service.UserDetailsServiceImpl;
import ec.edu.ups.icc.fundamentos01.security.utils.JwtUtil;

import java.io.IOException;

/**
 * JwtAuthenticationFilter: Filtro que valida JWT en CADA REQUEST
 */
@Component // Spring lo registra automáticamente como bean
public class JwtAuthenticationFilter extends OncePerRequestFilter {

    /**
     * Logger para debugging y errores
     * 
     * Niveles de log:
     * - logger.debug(): Solo en desarrollo (no aparece en producción)
     * - logger.error(): Errores críticos (aparece en producción)
     */
    private static final Logger logger = LoggerFactory.getLogger(JwtAuthenticationFilter.class);

    /**
     * Dependencias inyectadas por Spring
     */
    private final JwtUtil jwtUtil; // Para validar y extraer datos del JWT
    private final UserDetailsServiceImpl userDetailsService; // Para cargar usuario desde BD
    private final JwtProperties jwtProperties; // Configuración JWT (header, prefix)

    public JwtAuthenticationFilter(JwtUtil jwtUtil,
            UserDetailsServiceImpl userDetailsService,
            JwtProperties jwtProperties) {
        this.jwtUtil = jwtUtil;
        this.userDetailsService = userDetailsService;
        this.jwtProperties = jwtProperties;
    }

    /**
     * doFilterInternal: MÉTODO PRINCIPAL del filtro
     * 
     * Se ejecuta UNA VEZ por cada request HTTP
     * 
     * @param request:     Petición HTTP entrante
     * @param response:    Respuesta HTTP saliente
     * @param filterChain: Cadena de filtros restantes
     * 
     *                     IMPORTANTE:
     *                     - Este método NO debe lanzar excepciones
     *                     - Si hay error, solo logueamos y continuamos
     *                     - El SecurityContext quedará vacío → Spring Security
     *                     rechazará la petición
     */
    @Override
    protected void doFilterInternal(HttpServletRequest request,
            HttpServletResponse response,
            FilterChain filterChain) throws ServletException, IOException {
        try {
            /**
             * PASO 1: Extraer token del header Authorization
             */
            String jwt = getJwtFromRequest(request);

            /**
             * PASO 2: Validar y autenticar SOLO si hay token
             */
            if (StringUtils.hasText(jwt) && jwtUtil.validateToken(jwt)) {

                /**
                 * PASO 3: Extraer email del token
                 */
                String email = jwtUtil.getEmailFromToken(jwt);

                /**
                 * PASO 4: Cargar usuario desde base de datos
                 */
                UserDetails userDetails = userDetailsService.loadUserByUsername(email);

                /**
                 * PASO 5: Crear objeto Authentication
                 * 
                 * UsernamePasswordAuthenticationToken:
                 * - Implementación de Authentication de Spring Security
                 * - Aunque se llama "Password", NO usamos contraseña aquí
                 * - Ya validamos el JWT, no necesitamos validar password
                 * 
                 * Constructor con 3 parámetros:
                 * 
                 * @param principal:   El usuario (UserDetails)
                 * @param credentials: Credenciales (null porque ya autenticamos con JWT)
                 * @param authorities: Roles/permisos del usuario
                 */
                UsernamePasswordAuthenticationToken authentication = new UsernamePasswordAuthenticationToken(
                        userDetails, // Principal (el usuario)
                        null, // Credentials (no necesarias)
                        userDetails.getAuthorities() // Authorities (roles/permisos)
                );

                /**
                 * Establecer detalles adicionales de la request
                 * 
                 * WebAuthenticationDetailsSource:
                 * - Extrae información de la HttpServletRequest
                 * - IP del cliente
                 * - Session ID (si existe)
                 * - Otros metadatos de la petición
                 * 
                 * .buildDetails(request):
                 * - Crea objeto WebAuthenticationDetails
                 * - Útil para auditoría y logs
                 * 
                 * Ejemplo de details:
                 * {
                 * remoteAddress: "192.168.1.100",
                 * sessionId: null (porque somos stateless)
                 * }
                 */
                authentication.setDetails(new WebAuthenticationDetailsSource().buildDetails(request));

                /**
                 * PASO 6: Establecer autenticación en SecurityContext
                 * 
                 * SecurityContextHolder:
                 * - ThreadLocal que almacena el contexto de seguridad
                 * - ThreadLocal: Una variable por thread (cada request = thread diferente)
                 * - Permite acceder al usuario autenticado desde cualquier parte del código
                 * 
                 * .getContext():
                 * - Obtiene o crea el SecurityContext para este thread
                 * 
                 * .setAuthentication(authentication):
                 * - Almacena el objeto Authentication
                 * - A partir de ahora, el usuario está AUTENTICADO
                 * - Spring Security permitirá acceso a endpoints protegidos
                 * 
                 * ¿Cómo se usa después?
                 * 
                 * En controladores:
                 * 
                 * @AuthenticationPrincipal UserDetailsImpl currentUser
                 * 
                 *                          En servicios:
                 *                          Authentication auth =
                 *                          SecurityContextHolder.getContext().getAuthentication();
                 *                          UserDetailsImpl user = (UserDetailsImpl)
                 *                          auth.getPrincipal();
                 * 
                 *                          En @PreAuthorize:
                 *                          @PreAuthorize("hasRole('ADMIN')") ← Lee authorities
                 *                          de aquí
                 */
                SecurityContextHolder.getContext().setAuthentication(authentication);

                /**
                 * Log de debug: Solo en desarrollo
                 * 
                 * logger.debug():
                 * - Solo aparece si logging.level.root=DEBUG
                 * - NO aparece en producción (logging.level.root=INFO)
                 * - Útil para debugging durante desarrollo
                 * 
                 * Mensaje de ejemplo:
                 * "Usuario autenticado: pablo@example.com"
                 */
                logger.debug("Usuario autenticado: {}", email);
            }

        } catch (Exception ex) {
            /**
             * Manejo de errores: Solo loguear, NO lanzar excepción
             * 
             * ¿Por qué no lanzar la excepción?
             * - Si lanzamos excepción, la request se aborta completamente
             * - Mejor: Dejar que continúe sin autenticación
             * - Spring Security se encargará de rechazarla con 401
             * 
             */
            logger.error("No se pudo establecer la autenticación del usuario", ex);
        }

        /**
         * PASO 7: Continuar con la cadena de filtros
         */
        filterChain.doFilter(request, response);
    }

    /**
     * getJwtFromRequest: Método helper para extraer JWT del header
     * 
     * FLUJO:
     * 1. Lee header "Authorization"
     * 2. Verifica que empiece con "Bearer "
     * 3. Extrae solo el token (sin "Bearer ")
     * 4. Retorna token o null
     * 
     * @param request: Petición HTTP
     * @return String: Token JWT o null si no existe
     * 
     *         Ejemplo:
     *         Header: "Authorization: Bearer eyJhbGci..."
     *         Retorna: "eyJhbGci..."
     * 
     *         Header: "Authorization: Basic abc123" (no es Bearer)
     *         Retorna: null
     * 
     *         Sin header Authorization
     *         Retorna: null
     */
    private String getJwtFromRequest(HttpServletRequest request) {
        /**
         * 1. Leer header Authorization
         * 
         * request.getHeader(jwtProperties.getHeader()):
         * - jwtProperties.getHeader() = "Authorization"
         * - Lee el valor del header
         * - Retorna null si no existe
         * 
         * Ejemplo:
         * bearerToken = "Bearer eyJhbGciOiJIUzI1NiJ9..."
         */
        String bearerToken = request.getHeader(jwtProperties.getHeader());

        /**
         * 2. Validar y extraer token
         * 
         * StringUtils.hasText(bearerToken):
         * - Verifica que NO sea null, vacío o solo espacios
         * 
         * bearerToken.startsWith(jwtProperties.getPrefix()):
         * - jwtProperties.getPrefix() = "Bearer "
         * - Verifica que el header comience con "Bearer "
         * - Importante: Incluye el espacio después de "Bearer"
         * 
         * bearerToken.substring(jwtProperties.getPrefix().length()):
         * - Extrae desde la posición 7 (longitud de "Bearer ")
         * - Ejemplo: "Bearer abc123".substring(7) = "abc123"
         * - Retorna solo el token, sin el prefijo
         * 
         * Si NO cumple las condiciones:
         * - Retorna null
         * - El filtro NO procesará autenticación
         * - La request continuará sin autenticación
         */
        if (StringUtils.hasText(bearerToken) && bearerToken.startsWith(jwtProperties.getPrefix())) {
            return bearerToken.substring(jwtProperties.getPrefix().length());
        }

        return null;
    }
}```
### DataInitializer.java
```java
package ec.edu.ups.icc.fundamentos01.security.init;

import ec.edu.ups.icc.fundamentos01.security.models.RoleEntity;
import ec.edu.ups.icc.fundamentos01.security.models.RoleName;
import ec.edu.ups.icc.fundamentos01.security.repository.RoleRepository;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import ec.edu.ups.icc.fundamentos01.users.repository.UserRepository;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.boot.CommandLineRunner;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.stereotype.Component;

import java.util.HashSet;
import java.util.Set;

@Component
public class DataInitializer implements CommandLineRunner {

    private static final Logger logger = LoggerFactory.getLogger(DataInitializer.class);

    private final RoleRepository roleRepository;
    private final UserRepository userRepository;
    private final PasswordEncoder passwordEncoder;

    public DataInitializer(RoleRepository roleRepository,
            UserRepository userRepository,
            PasswordEncoder passwordEncoder) {
        this.roleRepository = roleRepository;
        this.userRepository = userRepository;
        this.passwordEncoder = passwordEncoder;
    }

    @Override
    public void run(String... args) throws Exception {
        // 1. Inicializar roles
        initializeRoles();

        // 2. Crear usuario admin por defecto
        createDefaultAdminUser();
    }

    private void initializeRoles() {
        logger.info("Inicializando roles...");

        for (RoleName roleName : RoleName.values()) {
            if (!roleRepository.existsByName(roleName)) {
                RoleEntity role = new RoleEntity(roleName, roleName.getDescription());
                roleRepository.save(role);
                logger.info("Rol creado: {}", roleName);
            }
        }

        logger.info("Roles inicializados correctamente");
    }

    private void createDefaultAdminUser() {
        logger.info("Verificando usuario administrador...");

        String adminEmail = "admin@ups.edu.ec";

        if (!userRepository.existsByEmail(adminEmail)) {
            UserEntity admin = new UserEntity();
            admin.setName("Administrador");
            admin.setEmail(adminEmail);
            admin.setPassword(passwordEncoder.encode("admin123"));

            // Asignar rol ADMIN
            RoleEntity adminRole = roleRepository.findByName(RoleName.ROLE_ADMIN)
                    .orElseThrow(() -> new RuntimeException("Rol ADMIN no encontrado"));

            Set<RoleEntity> roles = new HashSet<>();
            roles.add(adminRole);
            admin.setRoles(roles);

            userRepository.save(admin);
            logger.info("Usuario administrador creado: {}", adminEmail);
        } else {
            logger.info("Usuario administrador ya existe");
        }
    }
}```
### RoleEntity.java
```java
package ec.edu.ups.icc.fundamentos01.security.models;

import ec.edu.ups.icc.fundamentos01.core.entities.BaseModel;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import jakarta.persistence.*;
import java.util.HashSet;
import java.util.Set;

/**
 * ENTIDAD: Role (Rol de usuario)
 * 
 * Representa un rol en el sistema (ROLE_USER, ROLE_ADMIN, ROLE_MODERATOR).
 * Se relaciona ManyToMany con usuarios → Un usuario puede tener múltiples roles.
 * 
 * Tabla en BD: roles
 * Tabla intermedia: user_roles (creada automáticamente por JPA)
 */
@Entity
@Table(name = "roles")  // Nombre de la tabla en PostgreSQL
public class RoleEntity extends BaseModel {  // Hereda id, createdAt, updatedAt

    /**
     * Nombre del rol (enum para type-safety)
     * 
     * @Enumerated(EnumType.STRING): Guarda "ROLE_USER" en lugar de ordinal (0, 1, 2)
     * nullable = false: Campo obligatorio
     * unique = true: No pueden existir roles duplicados
     * length = 50: Máximo 50 caracteres en BD
     * 
     * Ejemplo en BD: "ROLE_USER", "ROLE_ADMIN"
     */
    @Column(nullable = false, unique = true, length = 50)
    @Enumerated(EnumType.STRING)  // Guardar nombre del enum, no el número
    private RoleName name;

    /**
     * Descripción del rol (opcional)
     * 
     * Ejemplo: "Usuario estándar con permisos básicos"
     */
    @Column(length = 200)
    private String description;

    /**
     * Relación INVERSA con usuarios (bidireccional)
     * 
     * @ManyToMany(mappedBy = "roles"): 
     *   - mappedBy indica que UserEntity es el DUEÑO de la relación
     *   - UserEntity tiene @JoinTable que crea la tabla intermedia user_roles
     * 
     * fetch = FetchType.LAZY: 
     *   - NO carga los usuarios automáticamente al consultar un rol
     *   - Se cargan solo cuando se accede a role.getUsers()
     *   - Mejora performance (evita cargar datos innecesarios)
     * 
     * Set<UserEntity>:
     *   - Set (no List) para evitar duplicados
     *   - HashSet por defecto (orden no importa)
     * 
     * Ejemplo:
     * RoleEntity adminRole = roleRepository.findByName(RoleName.ROLE_ADMIN);
     * Set<UserEntity> admins = adminRole.getUsers();  // ← Aquí se carga desde BD
     */
    @ManyToMany(mappedBy = "roles", fetch = FetchType.LAZY)
    private Set<UserEntity> users = new HashSet<>();

    // ============== CONSTRUCTORES ==============

    /**
     * Constructor vacío (REQUERIDO por JPA)
     * JPA usa reflexión para crear instancias
     */
    public RoleEntity() {
    }

    /**
     * Constructor con nombre de rol
     * Útil para crear roles en DataInitializer
     */
    public RoleEntity(RoleName name) {
        this.name = name;
    }

    /**
     * Constructor completo
     * Útil para crear roles con descripción
     */
    public RoleEntity(RoleName name, String description) {
        this.name = name;
        this.description = description;
    }

    public RoleName getName() {
        return name;
    }

    public void setName(RoleName name) {
        this.name = name;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public Set<UserEntity> getUsers() {
        return users;
    }

    public void setUsers(Set<UserEntity> users) {
        this.users = users;
    }

    // ============== GETTERS Y SETTERS ==============

    
   
}```
### RoleName.java
```java
package ec.edu.ups.icc.fundamentos01.security.models;

public enum RoleName {
    ROLE_USER("Usuario estándar con permisos básicos"),
    ROLE_ADMIN("Administrador con permisos completos"),
    ROLE_MODERATOR("Moderador con permisos intermedios");

    private final String description;

    RoleName(String description) {
        this.description = description;
    }

    public String getDescription() {
        return description;
    }
}```
### RolesRepository.java
```java
package ec.edu.ups.icc.fundamentos01.security.repository;


import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

import ec.edu.ups.icc.fundamentos01.security.models.RoleEntity;
import ec.edu.ups.icc.fundamentos01.security.models.RoleName;

import java.util.Optional;

@Repository
public interface RoleRepository extends JpaRepository<RoleEntity, Long> {

    // Buscar rol por nombre (ROLE_USER, ROLE_ADMIN, etc.)
    Optional<RoleEntity> findByName(RoleName name);
    
    // Verificar si existe un rol específico
    boolean existsByName(RoleName name);
}
```
### AuthService.java
```java
package ec.edu.ups.icc.fundamentos01.security.service;

// imports packages y clases....
import org.springframework.security.authentication.AuthenticationManager;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.Authentication;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import ec.edu.ups.icc.fundamentos01.exceptions.domain.BadRequestException;
import ec.edu.ups.icc.fundamentos01.exceptions.domain.ConflictException;
import ec.edu.ups.icc.fundamentos01.security.dtos.AuthResponseDto;
import ec.edu.ups.icc.fundamentos01.security.dtos.LoginRequestDto;
import ec.edu.ups.icc.fundamentos01.security.dtos.RegisterRequestDto;
import ec.edu.ups.icc.fundamentos01.security.models.RoleEntity;
import ec.edu.ups.icc.fundamentos01.security.models.RoleName;
import ec.edu.ups.icc.fundamentos01.security.repository.RoleRepository;
import ec.edu.ups.icc.fundamentos01.security.utils.JwtUtil;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import ec.edu.ups.icc.fundamentos01.users.repository.UserRepository;

import java.util.HashSet;
import java.util.Set;
import java.util.stream.Collectors;

@Service
public class AuthService {

    // Dependencias inyectadas para login y registro
    private final AuthenticationManager authenticationManager; // Valida credenciales
    private final UserRepository userRepository; // Acceso a BD
    private final RoleRepository roleRepository; // Gestión de roles
    private final PasswordEncoder passwordEncoder; // Hash de passwords
    private final JwtUtil jwtUtil; // Generación de tokens

    public AuthService(AuthenticationManager authenticationManager,
            UserRepository userRepository,
            RoleRepository roleRepository,
            PasswordEncoder passwordEncoder,
            JwtUtil jwtUtil) {
        this.authenticationManager = authenticationManager;
        this.userRepository = userRepository;
        this.roleRepository = roleRepository;
        this.passwordEncoder = passwordEncoder;
        this.jwtUtil = jwtUtil;
    }

    /**
     * Login: Valida credenciales y retorna JWT
     */
    @Transactional(readOnly = true) // Solo lectura, no modifica BD
    public AuthResponseDto login(LoginRequestDto loginRequest) {

        // 1. Validar email y password con Spring Security
        // authenticationManager usa UserDetailsService internamente
        // Si falla: lanza BadCredentialsException → 401
        Authentication authentication = authenticationManager.authenticate(
                new UsernamePasswordAuthenticationToken(
                        loginRequest.getEmail(),
                        loginRequest.getPassword()));

        // 2. Establecer usuario autenticado en contexto de seguridad
        // Permite acceso a usuario actual en servicios
        SecurityContextHolder.getContext().setAuthentication(authentication);

        // 3. Generar JWT con datos del usuario
        String jwt = jwtUtil.generateToken(authentication);

        // 4. Extraer información del usuario autenticado
        UserDetailsImpl userDetails = (UserDetailsImpl) authentication.getPrincipal();

        // Convertir authorities a Set<String> para la respuesta
        Set<String> roles = userDetails.getAuthorities().stream()
                .map(item -> item.getAuthority()) // "ROLE_USER", "ROLE_ADMIN"
                .collect(Collectors.toSet());

        // 5. Retornar JWT + datos del usuario
        return new AuthResponseDto(
                jwt, // Token para autenticación
                userDetails.getId(), // ID del usuario
                userDetails.getName(), // Nombre completo
                userDetails.getEmail(), // Email
                roles // Roles asignados
        );
    }

    /**
     * Registro: Crea nuevo usuario y retorna JWT automáticamente
     */
    @Transactional // Requiere transacción para INSERT
    public AuthResponseDto register(RegisterRequestDto registerRequest) {

        // 1. Validar que email no exista
        // Si existe: lanza ConflictException → 409
        if (userRepository.existsByEmail(registerRequest.getEmail())) {
            throw new ConflictException("El email ya está registrado");
        }

        // 2. Crear nueva entidad de usuario
        UserEntity user = new UserEntity();
        user.setName(registerRequest.getName());
        user.setEmail(registerRequest.getEmail());
        // Hash del password con BCrypt (nunca almacenar en texto plano)
        user.setPassword(passwordEncoder.encode(registerRequest.getPassword()));

        // 3. Asignar rol por defecto ROLE_USER
        // Si no existe: lanza BadRequestException → 400
        // Registro de usuario - asignar rol por defecto
        RoleEntity userRole = roleRepository.findByName(RoleName.ROLE_USER)
                .orElseThrow(() -> new BadRequestException("Rol por defecto no encontrado"));

        Set<RoleEntity> roles = new HashSet<>();
        roles.add(userRole);
        user.setRoles(roles);

        // 4. Guardar en BD (INSERT)
        user = userRepository.save(user);

        // 5. Generar JWT automáticamente para login directo
        // No requiere que el usuario haga login después de registrarse
        UserDetailsImpl userDetails = UserDetailsImpl.build(user);
        String jwt = jwtUtil.generateTokenFromUserDetails(userDetails);

        // Convertir roles a nombres de string
        Set<String> roleNames = user.getRoles().stream()
                .map(role -> role.getName().name()) // RoleName.ROLE_USER → "ROLE_USER"
                .collect(Collectors.toSet());

        // 6. Retornar JWT + datos del usuario registrado
        return new AuthResponseDto(
                jwt,
                user.getId(),
                user.getName(),
                user.getEmail(),
                roleNames);
    }
}```
### UserDetailsImpl.java
```java
package ec.edu.ups.icc.fundamentos01.security.service;

import org.springframework.security.core.userdetails.UserDetails;

import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;

import org.springframework.security.core.GrantedAuthority;
import org.springframework.security.core.authority.SimpleGrantedAuthority;

import java.util.Collection;
import java.util.stream.Collectors;

public class UserDetailsImpl implements UserDetails {

    private final Long id;
    private final String name;
    private final String email;
    private final String password;
    private final Collection<? extends GrantedAuthority> authorities;

    public UserDetailsImpl(Long id, String name, String email, String password,
                           Collection<? extends GrantedAuthority> authorities) {
        this.id = id;
        this.name = name;
        this.email = email;
        this.password = password;
        this.authorities = authorities;
    }

    /**
     * Factory method para crear UserDetailsImpl desde UserEntity
     */
    public static UserDetailsImpl build(UserEntity user) {
        // Convertir roles a authorities de Spring Security
        Collection<GrantedAuthority> authorities = user.getRoles().stream()
            .map(role -> new SimpleGrantedAuthority(role.getName().name()))
            .collect(Collectors.toList());

        return new UserDetailsImpl(
            user.getId(),
            user.getName(),
            user.getEmail(),
            user.getPassword(),
            authorities
        );
    }

    // ============== GETTERS ==============


    
    // ============== MÉTODOS DE UserDetails ==============

    @Override
    public Collection<? extends GrantedAuthority> getAuthorities() {
        return authorities;
    }

    @Override
    public String getPassword() {
        return password;
    }

    @Override
    public String getUsername() {
        return email;  // Usamos email como username
    }

    @Override
    public boolean isAccountNonExpired() {
        return true;
    }

    @Override
    public boolean isAccountNonLocked() {
        return true;
    }

    @Override
    public boolean isCredentialsNonExpired() {
        return true;
    }

    @Override
    public boolean isEnabled() {
        return true;
    }

    public Long getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public String getEmail() {
        return email;
    }
}
```
### UserDetailsServiceImpl.java
```java
package ec.edu.ups.icc.fundamentos01.security.service;

// imports packages y clases....

import org.springframework.security.core.userdetails.UserDetails;
import org.springframework.security.core.userdetails.UserDetailsService;
import org.springframework.security.core.userdetails.UsernameNotFoundException;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import ec.edu.ups.icc.fundamentos01.users.repository.UserRepository;

/**
 * UserDetailsServiceImpl: Carga usuarios desde la base de datos
 */
@Service // Componente de Spring (se inyecta automáticamente)
public class UserDetailsServiceImpl implements UserDetailsService {

    /**
     * Repositorio para acceder a la base de datos
     * 
     * Inyectado por Spring automáticamente (constructor injection)
     */
    private final UserRepository userRepository;

    /**
     * Constructor: Spring inyecta UserRepository automáticamente
     * 
     * @param userRepository: Repositorio de usuarios
     */
    public UserDetailsServiceImpl(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    /**
     * loadUserByUsername: MÉTODO PRINCIPAL de UserDetailsService
     * 
     * SecurityContext.setAuthentication(userDetails)
     * 
     * @param email: Email del usuario (lo llamamos username por el contrato)
     * @return UserDetails: Usuario convertido a formato Spring Security
     * @throws UsernameNotFoundException: Si el usuario no existe
     * 
     * @Transactional(readOnly = true):
     *                         - readOnly = true: Optimización para consultas SELECT
     *                         - Permite a Hibernate/PostgreSQL optimizar la query
     *                         - NO permite operaciones de escritura (INSERT,
     *                         UPDATE, DELETE)
     *                         - Si intentamos modificar, lanza excepción
     */
    @Override
    @Transactional(readOnly = true)
    public UserDetails loadUserByUsername(String email) throws UsernameNotFoundException {
        /**
         * 1. Buscar usuario por email en la base de datos
         * 
         * Nota: Los roles se cargan automáticamente por FetchType.EAGER
         */
        UserEntity user = userRepository.findByEmail(email)
                /**
                 * .orElseThrow(): Si Optional está vacío, lanza excepción
                 */
                .orElseThrow(() -> new UsernameNotFoundException(
                        "Usuario no encontrado con email: " + email));

        /**
         * 2. Convertir UserEntity → UserDetailsImpl
         * 
         * UserDetailsImpl.build(user):
         * - Factory method que convierte nuestro UserEntity
         * - Extrae roles y los convierte a authorities
         * - Retorna objeto compatible con Spring Security
         * 
         */
        return UserDetailsImpl.build(user);
    }
}
```
### JwtUtil.java
```java
package ec.edu.ups.icc.fundamentos01.security.utils;


import io.jsonwebtoken.*;
import io.jsonwebtoken.security.Keys;
import io.jsonwebtoken.security.SignatureException;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.security.core.Authentication;
import org.springframework.security.core.GrantedAuthority;
import org.springframework.stereotype.Component;

import ec.edu.ups.icc.fundamentos01.security.config.JwtProperties;
import ec.edu.ups.icc.fundamentos01.security.service.UserDetailsImpl;

import javax.crypto.SecretKey;
import java.util.Date;
import java.util.stream.Collectors;

@Component
public class JwtUtil {

    private static final Logger logger = LoggerFactory.getLogger(JwtUtil.class);

    private final JwtProperties jwtProperties;
    private final SecretKey key;

    /**
     * Constructor: Inicializa JwtUtil con propiedades y clave secreta
     * 
     * @param jwtProperties: Inyectado automáticamente por Spring
     *                        Contiene: secret, expiration, issuer, etc.
     */
    public JwtUtil(JwtProperties jwtProperties) {
        this.jwtProperties = jwtProperties;
        
        /**
         * Genera clave segura para algoritmo HS256
         * 
         * Keys.hmacShaKeyFor(): Convierte String a SecretKey
         * .getBytes(): Convierte String a byte array
         * 
         * Requisitos:
         * - Mínimo 256 bits (32 caracteres) para HS256
         * - Si es menor, lanza WeakKeyException
         * 
         * Ejemplo:
         * secret = "mySecretKeyForJWT2024MustBeAtLeast256BitsLongForHS256Algorithm"
         * key = SecretKey basada en esos bytes
         * 
         * Esta key se usa para:
         * - Firmar tokens al generarlos (signWith)
         * - Verificar tokens al validarlos (verifyWith)
         */
        this.key = Keys.hmacShaKeyFor(jwtProperties.getSecret().getBytes());
    }

    /**
     * Genera un token JWT desde la autenticación
     * 
     * Se usa en el FLUJO DE LOGIN:
     * 1. Usuario envía email/password
     * 2. AuthenticationManager valida credenciales
     * 3. Se llama a este método para generar el token
     * 
     * @param authentication: Objeto Authentication de Spring Security
     *                        Contiene el usuario autenticado
     * @return String: Token JWT completo ("eyJhbGciOiJIUzI1NiJ9...")
     */
    public String generateToken(Authentication authentication) {
        // 1. Extraer información del usuario autenticado
        //    Cast seguro porque siempre retorna UserDetailsImpl
        UserDetailsImpl userPrincipal = (UserDetailsImpl) authentication.getPrincipal();

        // 2. Calcular fechas de emisión y expiración
        Date now = new Date();  // Fecha actual
        Date expiryDate = new Date(now.getTime() + jwtProperties.getExpiration());
        // Ejemplo: now = 2024-01-26 10:00:00
        //          expiration = 1800000 ms (30 minutos)
        //          expiryDate = 2024-01-26 10:30:00

        // 3. Extraer roles del usuario y convertir a String
        //    Ejemplo: [ROLE_USER, ROLE_ADMIN] → "ROLE_USER,ROLE_ADMIN"
        String roles = userPrincipal.getAuthorities().stream()
            .map(GrantedAuthority::getAuthority)  // Extrae "ROLE_USER", "ROLE_ADMIN"
            .collect(Collectors.joining(","));     // Une con comas

        // 4. Construir y firmar el token JWT
        return Jwts.builder()
            // Subject: Identificador único del usuario (su ID)
            .subject(String.valueOf(userPrincipal.getId()))  // "1"
            
            // Claims personalizados (datos adicionales en el payload)
            .claim("email", userPrincipal.getEmail())     // "pablo@example.com"
            .claim("name", userPrincipal.getName())       // "Pablo Torres"
            .claim("roles", roles)                        // "ROLE_USER,ROLE_ADMIN"
            
            // Issuer: Quién emitió el token
            .issuer(jwtProperties.getIssuer())            // "fundamentos01-api"
            
            // Fechas
            .issuedAt(now)                                // Cuándo se creó
            .expiration(expiryDate)                       // Cuándo expira
            
            // Firma digital con algoritmo HS256
            .signWith(key, Jwts.SIG.HS256)                // Firma con clave secreta
            
            // Compactar: Genera el String final
            .compact();  // → "eyJhbGci...header.eyJzdWI...payload.firma"
    }

    /**
     * Genera un token JWT desde UserDetailsImpl directamente
     * 
     * Se usa en el FLUJO DE REGISTRO:
     * 1. Usuario se registra
     * 2. Se crea UserEntity en BD
     * 3. Se convierte a UserDetailsImpl
     * 4. Se llama a este método (sin necesidad de autenticar primero)
     * 
     * Similar a generateToken() pero sin objeto Authentication
     */
    public String generateTokenFromUserDetails(UserDetailsImpl userDetails) {
        Date now = new Date();
        Date expiryDate = new Date(now.getTime() + jwtProperties.getExpiration());

        String roles = userDetails.getAuthorities().stream()
            .map(GrantedAuthority::getAuthority)
            .collect(Collectors.joining(","));

        return Jwts.builder()
            .subject(String.valueOf(userDetails.getId()))
            .claim("email", userDetails.getEmail())
            .claim("name", userDetails.getName())
            .claim("roles", roles)
            .issuer(jwtProperties.getIssuer())
            .issuedAt(now)
            .expiration(expiryDate)
            .signWith(key, Jwts.SIG.HS256)
            .compact();
    }

    /**
     * Extrae el ID de usuario del token
     * 
     * Se usa en JwtAuthenticationFilter para:
     * 1. Validar el token
     * 2. Extraer el ID del usuario
     * 3. Cargar el usuario desde BD
     * 
     * @param token: Token JWT (sin "Bearer ")
     * @return Long: ID del usuario
     */
    public Long getUserIdFromToken(String token) {
        // 1. Parsear y validar el token
        Claims claims = Jwts.parser()
            .verifyWith(key)              // Verifica firma con clave secreta
            .build()                      // Construye el parser
            .parseSignedClaims(token)     // Parsea el token
            .getPayload();                // Obtiene el payload (claims)

        // 2. Extraer el subject (ID del usuario)
        //    subject = "1" (guardado como String en el token)
        //    Long.parseLong("1") = 1L
        return Long.parseLong(claims.getSubject());
    }

    /**
     * Extrae el email del token
     * 
     * Similar a getUserIdFromToken pero extrae un claim personalizado
     */
    public String getEmailFromToken(String token) {
        Claims claims = Jwts.parser()
            .verifyWith(key)
            .build()
            .parseSignedClaims(token)
            .getPayload();

        // Extraer claim "email" como String
        return claims.get("email", String.class);
    }

    /**
     * Valida el token JWT
     * 
     * VERIFICA:
     * 1. Firma: ¿El token fue firmado por nosotros?
     * 2. Formato: ¿El token tiene estructura correcta?
     * 3. Expiración: ¿El token aún es válido?
     * 
     * Se usa en JwtAuthenticationFilter en CADA REQUEST
     * 
     * @param authToken: Token completo (sin "Bearer ")
     * @return boolean: true si válido, false si inválido
     */
    public boolean validateToken(String authToken) {
        try {
            // Intenta parsear el token
            // Si algo falla, lanza excepción
            Jwts.parser()
                .verifyWith(key)              // Verifica firma con nuestra clave
                .build()
                .parseSignedClaims(authToken);
            
            // Si llegamos aquí, el token es VÁLIDO
            return true;
            
        } catch (SignatureException ex) {
            // Firma inválida: Token modificado o clave incorrecta
            // Ejemplo: Alguien cambió el payload pero no puede firmar correctamente
            logger.error("Firma JWT inválida: {}", ex.getMessage());
            
        } catch (MalformedJwtException ex) {
            // Token malformado: No tiene estructura correcta (header.payload.signature)
            // Ejemplo: "abc123" en lugar de token válido
            logger.error("Token JWT malformado: {}", ex.getMessage());
            
        } catch (ExpiredJwtException ex) {
            // Token expirado: Pasaron más de 30 minutos desde su creación
            // Ejemplo: Token creado a las 10:00, ahora son las 10:35
            logger.error("Token JWT expirado: {}", ex.getMessage());
            
        } catch (UnsupportedJwtException ex) {
            // Token no soportado: Usa algoritmo que no soportamos
            // Ejemplo: Token firmado con RS256 pero esperamos HS256
            logger.error("Token JWT no soportado: {}", ex.getMessage());
            
        } catch (IllegalArgumentException ex) {
            // Claims vacío: Token sin payload
            logger.error("JWT claims string está vacío: {}", ex.getMessage());
        }
        
        // Si cayó en cualquier catch, el token es INVÁLIDO
        return false;
    }
}
```

### UserController.java
```java
package ec.edu.ups.icc.fundamentos01.users.controllers;

import java.util.List;

import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.DeleteMapping;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PatchMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.PutMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.CreateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.PartialUpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UserResponseDto;

import ec.edu.ups.icc.fundamentos01.users.services.UserService;
import jakarta.validation.Valid;

@RestController
@RequestMapping("/api/users")
public class UsersController {

    private UserService userService;

    public UsersController(UserService userService) {
        this.userService = userService;
    }

    @GetMapping
    public List<UserResponseDto> findAll() {
        return userService.findAll();
    }

    @GetMapping("/{id}")
    public UserResponseDto findOne(@PathVariable("id") int id) {
        return userService.findOne(id);
    }

    @PostMapping
    public UserResponseDto create(@Valid @RequestBody CreateUserDto dto) {
        return userService.create(dto);
    }

    @PutMapping("/{id}")
    public UserResponseDto update(@PathVariable("id") int id, @RequestBody UpdateUserDto dto) {
        return userService.update(id, dto);
    }

    @PatchMapping("/{id}")
    public UserResponseDto partialUpdate(@PathVariable("id") int id, @RequestBody PartialUpdateUserDto dto) {
        return userService.partialUpdate(id, dto);
    }

    @DeleteMapping("/{id}")
    public void delete(@PathVariable("id") int id) {
        userService.delete(id);
    }

    @GetMapping("/{id}/products")
    public ResponseEntity<List<ProductResponseDto>> getProducts(
            @PathVariable("id") Long id) {

        List<ProductResponseDto> products = userService.getProductsByUserId(id);
        return ResponseEntity.ok(products);
    }

    // ============== ENDPOINT AVANZADO: PRODUCTOS CON FILTROS ==============

    /**
     * Obtiene productos de un usuario con filtros opcionales
     * Ejemplo: GET
     * /api/users/5/products-v2?name=laptop&minPrice=500&maxPrice=2000&categoryId=3
     */

    @GetMapping("/{id}/products-v2")
    public ResponseEntity<List<ProductResponseDto>> getProductsWithFilters(
            @PathVariable("id") Long id,
            @RequestParam(value = "name", required = false) String name,
            @RequestParam(value = "minPrice", required = false) Double minPrice,
            @RequestParam(value = "maxPrice", required = false) Double maxPrice,
            @RequestParam(value = "categoryId", required = false) Long categoryId) {

        List<ProductResponseDto> products = userService.getProductsByUserIdWithFilters(
                id, name, minPrice, maxPrice, categoryId);

        return ResponseEntity.ok(products);
    }
}
```
### CreateUserDto.java
```java
package ec.edu.ups.icc.fundamentos01.users.dtos;

import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.Size;

public class CreateUserDto {
  @NotBlank(message = "El nombre es obligatorio")
  @Size(min = 3, max = 150, message = "El nombre debe tener entre 3 y 150 caracteres")
  public String name;

  @NotBlank(message = "El email es obligatorio")
  @Email(message = "Debe ingresar un email válido")
  @Size(max = 150)
  public String email;

  @NotBlank(message = "La contraseña es obligatoria")
  @Size(min = 8, message = "La contraseña debe tener al menos 8 caracteres")
  public String password;
}
```
### PartialUpdateUserDto.java
```java
package ec.edu.ups.icc.fundamentos01.users.dtos;

import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.Size;

public class PartialUpdateUserDto {

    @Size(min = 3, max = 150)
    public String name;

    @Email
    @Size(max = 150)
    public String email;

    @Size(min = 8)
    public String password;
}```
### UpdateUserDto.java
```java
package ec.edu.ups.icc.fundamentos01.users.dtos;

import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.Size;

public class UpdateUserDto {

    @NotBlank
    @Size(min = 3, max = 150)
    public String name;

    @NotBlank
    @Email
    @Size(max = 150)
    public String email;

    @NotBlank
    @Size(min = 8)
    public String password;
}```
### UserResposeDto.java
```java
package ec.edu.ups.icc.fundamentos01.users.dtos;

public class UserResponseDto {
    public int id;
    public String name;
    public String email;
}

```

### UserMapper.java
```java
package ec.edu.ups.icc.fundamentos01.users.mappers;


import ec.edu.ups.icc.fundamentos01.users.dtos.CreateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UserResponseDto;
import ec.edu.ups.icc.fundamentos01.users.models.User;

public class UserMapper {

    public static User toModel(int id, String name, String email) {
        return new User(id, name, email, "secret");
    }

    // DTO -> Model
    public static User fromCreateDto(CreateUserDto dto) {
        return new User(0, dto.name, dto.email, dto.password);
    }   
    public static User fromUpdateDto(UpdateUserDto dto) {
        return new User(0, dto.name, dto.email, dto.password);
    }   


    public static UserResponseDto toResponse(User user) {
         UserResponseDto dto = new UserResponseDto();
        dto.id = user.getId();
        dto.name = user.getName();
        dto.email = user.getEmail();
        return dto;
    }
}```

### User.java
```java
package ec.edu.ups.icc.fundamentos01.users.models;

import ec.edu.ups.icc.fundamentos01.users.dtos.PartialUpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UpdateUserDto;

public class User {

    private int id;
    private String name;
    private String email;
    private String password; // no se expone en la API
    private String createdAt;

    // Constructor privado para forzar uso de factory methods
    public User(int id, String name, String email, String password) {
        this.id = id;
        this.name = name;
        this.email = email;
        this.password = password;
        this.createdAt = java.time.LocalDateTime.now().toString();
    }


    // ==================== FACTORY METHODS ====================
   /**
     * Crea un User desde una entidad persistente
     * @param entity Entidad recuperada de la BD
     * @return instancia de User para lógica de negocio
     */
    public static User fromEntity(UserEntity entity) {
        return new User(
            entity.getId().intValue(),
            entity.getName(),
            entity.getEmail(),
            entity.getPassword()
        );
    }

        /**
     * Convierte este User a una entidad persistente
     * @return UserEntity lista para guardar en BD
     */
    public UserEntity toEntity() {
        UserEntity entity = new UserEntity();
        if (this.id > 0) {
            entity.setId((long) this.id);
        }
        entity.setName(this.name);
        entity.setEmail(this.email);
        entity.setPassword(this.password);
        return entity;
    }


    public User update(UpdateUserDto dto) {
    this.name = dto.name;
    this.email = dto.email;
    return this;
}
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    } 

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    public String getCreatedAt() {
        return createdAt;
    }

    public void setCreatedAt(String createdAt) {
        this.createdAt = createdAt;
    }


    public User partialUpdate(PartialUpdateUserDto dto) {
       
    if (dto.name != null) {
        this.name = dto.name;
    }

    if (dto.email != null) {
        this.email = dto.email;
    }

      if (dto.password != null) {
        this.password = dto.password;
    }

    return this;
    }


}```
### UserEntity.java
```java
package ec.edu.ups.icc.fundamentos01.users.models;

import java.util.HashSet;
import java.util.List;
import java.util.Set;

import ec.edu.ups.icc.fundamentos01.core.entities.BaseModel;
import ec.edu.ups.icc.fundamentos01.products.models.ProductEntity;
import ec.edu.ups.icc.fundamentos01.security.models.RoleEntity;
import ec.edu.ups.icc.fundamentos01.security.models.RoleName;
import jakarta.persistence.*;

@Entity
@Table(name = "users")
public class UserEntity extends BaseModel {

    @Column(nullable = false, length = 150)
    private String name;

    @Column(nullable = false, unique = true, length = 150)
    private String email;

    @Column(nullable = false)
    private String password;

    /**
     * Relación One-to-Many con Product
     * Un usuario puede tener múltiples productos
     */

    @ManyToMany(fetch = FetchType.EAGER)
    @JoinTable(name = "user_roles", joinColumns = @JoinColumn(name = "user_id"), inverseJoinColumns = @JoinColumn(name = "role_id"))

    private Set<RoleEntity> roles = new HashSet<>();

    @OneToMany(mappedBy = "owner", fetch = FetchType.LAZY)
    private List<ProductEntity> products;

    public UserEntity() {
    }

    public UserEntity(String name, String email, String password) {
        this.name = name;
        this.email = email;
        this.password = password;
    }


    public Set<RoleEntity> getRoles() {
        return roles;
    }

    public void setRoles(Set<RoleEntity> roles) {
        this.roles = roles;
    }

    public List<ProductEntity> getProducts() {
        return products;
    }

    public void setProducts(List<ProductEntity> products) {
        this.products = products;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    // ============== MÉTODOS HELPER ==============

    /**
     * Agrega un rol al usuario
     */
    public void addRole(RoleEntity role) {
        this.roles.add(role);
        role.getUsers().add(this);
    }

    /**
     * Verifica si el usuario tiene un rol específico
     */
        public boolean hasRole(RoleName roleName) {
        return this.roles.stream()
                .anyMatch(role -> role.getName().equals(roleName));
    }

}```

### UserRepository.java
```java
package ec.edu.ups.icc.fundamentos01.users.repository;

import java.util.Optional;

import org.springframework.data.jpa.repository.JpaRepository;

import org.springframework.stereotype.Repository;

import ec.edu.ups.icc.fundamentos01.products.models.ProductEntity;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;

@Repository
public interface UserRepository extends JpaRepository<UserEntity, Long> {

    Optional<UserEntity> findByEmail(String email);

    Optional<ProductEntity> findByName(String name);

    // Verificar si email ya está registrado (usado en registro)
    boolean existsByEmail(String email);

}```

### UserService.java
```java
package ec.edu.ups.icc.fundamentos01.users.services;

import java.util.List;

import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.CreateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.PartialUpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UserResponseDto;

public interface UserService {

    List<UserResponseDto> findAll();

    UserResponseDto findOne(int id);

    UserResponseDto create(CreateUserDto dto);

    UserResponseDto update(int id, UpdateUserDto dto);

    UserResponseDto partialUpdate(int id, PartialUpdateUserDto dto);

    void delete(int id);

    List<ProductResponseDto> getProductsByUserId(Long userId);

    List<ProductResponseDto> getProductsByUserIdWithFilters(
            Long userId,
            String name,
            Double minPrice,
            Double maxPrice,
            Long categoryId);
}
```
### UserServciceImpl.java
```java
package ec.edu.ups.icc.fundamentos01.users.services;

import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

import org.springframework.stereotype.Service;

import ec.edu.ups.icc.fundamentos01.categories.dtos.CategoryResponseDto;
import ec.edu.ups.icc.fundamentos01.categories.entity.CategoryEntity;
import ec.edu.ups.icc.fundamentos01.exceptions.domain.BadRequestException;
import ec.edu.ups.icc.fundamentos01.exceptions.domain.NotFoundException;
import ec.edu.ups.icc.fundamentos01.products.dtos.ProductResponseDto;

import ec.edu.ups.icc.fundamentos01.products.models.ProductEntity;
import ec.edu.ups.icc.fundamentos01.products.repository.ProductRepository;
import ec.edu.ups.icc.fundamentos01.users.dtos.CreateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.PartialUpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UpdateUserDto;
import ec.edu.ups.icc.fundamentos01.users.dtos.UserResponseDto;
import ec.edu.ups.icc.fundamentos01.users.mappers.UserMapper;
import ec.edu.ups.icc.fundamentos01.users.models.User;
import ec.edu.ups.icc.fundamentos01.users.models.UserEntity;
import ec.edu.ups.icc.fundamentos01.users.repository.UserRepository;

@Service
public class UserServiceImpl implements UserService {
    private final UserRepository userRepo;
    private final ProductRepository productRepo;

    public UserServiceImpl(UserRepository userRepo, ProductRepository productRepo) {
        this.userRepo = userRepo;
        this.productRepo = productRepo;
    }

    @Override
    public List<UserResponseDto> findAll() {
        return userRepo.findAll()
                .stream()
                .map(User::fromEntity) // Entity → Domain
                .map(UserMapper::toResponse) // Domain → DTO
                .toList();
    }

    @Override
    public UserResponseDto findOne(int id) {
        return userRepo.findById((long) id)
                .map(User::fromEntity)
                .map(UserMapper::toResponse)
                .orElseThrow(() -> new NotFoundException("Usuario no encontrado"));
    }

    @Override
    public UserResponseDto create(CreateUserDto dto) {

        // Regla: email único
        if (userRepo.findByEmail(dto.email).isPresent()) {
            throw new IllegalStateException("El email ya está registrado");
        }

        User user = UserMapper.fromCreateDto(dto);

        UserEntity saved = userRepo.save(user.toEntity());

        return UserMapper.toResponse(User.fromEntity(saved));

    }

    @Override
    public UserResponseDto update(int id, UpdateUserDto dto) {

        return userRepo.findById((long) id)
                // Entity → Domain
                .map(User::fromEntity)

                // Aplicar cambios permitidos en el dominio
                .map(u -> u.update(dto))

                // Domain → Entity
                .map(User::toEntity)

                // Persistencia
                .map(userRepo::save)

                // Entity → Domain
                .map(User::fromEntity)

                // Domain → DTO
                .map(UserMapper::toResponse)

                // Error controlado si no existe
                .orElseThrow(() -> new IllegalStateException("Usuario no encontrado"));
    }

    @Override
    public UserResponseDto partialUpdate(int id, PartialUpdateUserDto dto) {

        return userRepo.findById((long) id)
                // Entity → Domain
                .map(User::fromEntity)

                // Aplicar solo los cambios presentes
                .map(user -> user.partialUpdate(dto))

                // Domain → Entity
                .map(User::toEntity)

                // Persistencia
                .map(userRepo::save)

                // Entity → Domain
                .map(User::fromEntity)

                // Domain → DTO
                .map(UserMapper::toResponse)

                // Error si no existe
                .orElseThrow(() -> new IllegalStateException("Usuario no encontrado"));
    }

    @Override
    public void delete(int id) {

        // Verifica existencia y elimina
        userRepo.findById((long) id)
                .ifPresentOrElse(
                        userRepo::delete,
                        () -> {
                            throw new IllegalStateException("Usuario no encontrado");
                        });
    }

    @Override
    public List<ProductResponseDto> getProductsByUserId(Long userId) {

        // 1. Validar que el usuario existe
        if (!userRepo.existsById(userId)) {
            throw new NotFoundException("Usuario no encontrado con ID: " + userId);
        }

        // 2. Consulta explícita al repositorio correcto
        List<ProductEntity> products = productRepo.findByOwnerId(userId);

        /*
         * Flujo correcto:
         * ProductEntity → ProductResponseDto
         *
         * No se pasa por el dominio (Product) porque:
         * - Es un endpoint de solo lectura (GET)
         * - No se aplican reglas de negocio
         * - El dominio no agrega valor en este caso
         * - Evitamos perder relaciones (user, categories)
         */
        // 3. Mapear a DTOs
        return products.stream()
                .map(this::toResponseDto)
                .collect(Collectors.toList());
    }

    @Override
    public List<ProductResponseDto> getProductsByUserIdWithFilters(
            Long userId,
            String name,
            Double minPrice,
            Double maxPrice,
            Long categoryId) {

        // Verificar que el usuario existe
        if (!userRepo.existsById(userId)) {
            throw new NotFoundException("Usuario no encontrado");
        }

        // 2. Validaciones de filtros
        if (minPrice != null && minPrice < 0) {
            throw new BadRequestException("El precio mínimo no puede ser negativo");
        }

        if (maxPrice != null && maxPrice < 0) {
            throw new BadRequestException("El precio máximo no puede ser negativo");
        }

        if (minPrice != null && maxPrice != null && maxPrice < minPrice) {
            throw new BadRequestException("El precio máximo debe ser mayor o igual al precio mínimo");
        }

        // 3. Consulta con filtros al repositorio correcto
        List<ProductEntity> products = productRepo.findByOwnerIdWithFilters(
                userId, name, minPrice, maxPrice, categoryId);

        // 4. Mapear a DTOs
        return products.stream()
                .map(this::toResponseDto)
                .collect(Collectors.toList());
    }

    // ============== MÉTODO HELPER ==============

    /**
     * Convierte ProductEntity a ProductResponseDto
     * NOTA: Este método podría estar en un mapper separado para mejor organización
     */
    private ProductResponseDto toResponseDto(ProductEntity entity) {
        ProductResponseDto dto = new ProductResponseDto();
        dto.id = entity.getId();
        dto.name = entity.getName();
        dto.price = entity.getPrice();
        dto.description = entity.getDescription();

        ProductResponseDto.UserSummaryDto ownerDto = new ProductResponseDto.UserSummaryDto();
        ownerDto.id = entity.getOwner().getId();
        ownerDto.name = entity.getOwner().getName();
        ownerDto.email = entity.getOwner().getEmail();

        List<CategoryResponseDto> categoryDtos = new ArrayList<>();
        for (CategoryEntity categoryEntity : entity.getCategories()) {
            CategoryResponseDto categoryDto = new CategoryResponseDto();
            categoryDto.id = categoryEntity.getId();
            categoryDto.name = categoryEntity.getName();
            categoryDto.description = categoryEntity.getDescription();
            categoryDtos.add(categoryDto);
        }
        dto.user = ownerDto;
        dto.categories = categoryDtos;
        return dto;

    }

}```
### Fundamentos01ApplicationTests.java
```java
package ec.edu.ups.icc.fundamentos01;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Fundamentos01Application {

	public static void main(String[] args) {
		SpringApplication.run(Fundamentos01Application.class, args);
	}

}
```

### build.gradle.kts
```java
plugins {
	java
	id("org.springframework.boot") version "4.0.0"
	id("io.spring.dependency-management") version "1.1.7"
}

group = "ec.edu.ups.icc"
version = "0.0.1-SNAPSHOT"
description = "Demo project for Spring Boot"

java {
	toolchain {
		languageVersion = JavaLanguageVersion.of(17)
	}
}

repositories {
	mavenCentral()
}

dependencies {
	implementation("org.springframework.boot:spring-boot-starter-webmvc")
	developmentOnly("org.springframework.boot:spring-boot-devtools")
	testImplementation("org.springframework.boot:spring-boot-starter-webmvc-test")
	testRuntimeOnly("org.junit.platform:junit-platform-launcher")
	implementation ("org.springframework.boot:spring-boot-starter-actuator")

	implementation("org.springframework.boot:spring-boot-starter-data-jpa")
	
    runtimeOnly("org.postgresql:postgresql")

	implementation("org.springframework.boot:spring-boot-starter-validation")

	
	// ============== NUEVAS DEPENDENCIAS DE SEGURIDAD ==============
	
	// Spring Security
	implementation("org.springframework.boot:spring-boot-starter-security")
	
	// JWT - JSON Web Token
	implementation("io.jsonwebtoken:jjwt-api:0.12.3")
	runtimeOnly("io.jsonwebtoken:jjwt-impl:0.12.3")
	runtimeOnly("io.jsonwebtoken:jjwt-jackson:0.12.3")
	
	// Jackson para manejo de fechas Java 8+ (LocalDateTime, LocalDate, etc.)
	// NECESARIO: ErrorResponse usa LocalDateTime que requiere este módulo
	implementation("com.fasterxml.jackson.datatype:jackson-datatype-jsr310")
	
	// Tests de seguridad
	testImplementation("org.springframework.security:spring-security-test")

}

tasks.withType<Test> {
	useJUnitPlatform()
}

tasks.withType<JavaCompile> {
	options.compilerArgs.add("-parameters")
}

```
### aplication.yaml

```java
spring:
    application:
        name: fundamentos01
    datasource:
        url: jdbc:postgresql://${DB_HOST:localhost}:${DB_PORT:5432}/${DB_NAME:devdb}
        username: ${DB_USERNAME:ups}
        password: ${DB_PASSWORD:ups123}
    jpa:
        hibernate:
            ddl-auto: update
        show-sql: true
        properties:
            hibernate:
                format_sql: true
                dialect: org.hibernate.dialect.PostgreSQLDialect
server:
    port: 8080

# ============== CONFIGURACIÓN DE JWT ==============
jwt:
    # Secret key para firmar tokens (EN PRODUCCIÓN USAR VARIABLE DE ENTORNO)
    secret: ${JWT_SECRET:mySecretKeyForJWT2024MustBeAtLeast256BitsLongForHS256Algorithm}
    
    # Tiempo de expiración del access token (30 minutos)
    expiration: 1800000  # 30 minutos en milisegundos
    
    # Tiempo de expiración del refresh token (7 días)
    refresh-expiration: 604800000  # 7 días en milisegundos
    
    # Issuer del token
    issuer: fundamentos01-api
    
    # Header donde se envía el token
    header: Authorization
    
    # Prefijo del token
    prefix: "Bearer "
```
